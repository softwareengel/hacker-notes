---
title:
tags:
date: 2026-03-06
toc: true
toc_sticky: true
---


# raspi-monitoring

``` bash 
pi@raspberrypi:~ $ uname -a
Linux raspberrypi 6.12.47+rpt-rpi-v8 #1 SMP PREEMPT Debian 1:6.12.47-1+rpt1 (2025-09-16) aarch64 GNU/Linux

```


## install docker 

``` bash 
sudo apt-get remove -y docker docker-engine docker.io containerd runc docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin 2>/dev/null; echo "Alte Pakete entfernt"

sudo apt-get update

curl -fsSL https://get.docker.com -o get-docker.sh && sudo sh get-docker.sh

sudo usermod -aG docker $USER && echo "Benutzer '$USER' zur Docker-Gruppe hinzugefügt"

sudo docker --version && sudo docker info | head -20

sudo docker run --rm hello-world

rm -f get-docker.sh && echo "Installationsskript entfernt"

```

## install portainer 


``` bash 

sudo docker volume create portainer_data

sudo docker run -d -p 8000:8000 -p 9443:9443 --name portainer --restart=always -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer-ce:latest
sudo docker ps --filter name=portainer
hostname -I | awk '{print $1}'
```

- HTTPS: `https://10.10.10.35:9443`
- HTTP (Edge Agent): `http://10.10.10.35:8000`


## install loki 

```
mkdir -p ~/loki
sudo docker run -d --name loki --restart=always -p 3100:3100 -v ~/loki/loki-config.yaml:/etc/loki/local-config.yaml grafana/loki:latest
sudo docker ps --filter name=loki
curl -s http://localhost:3100/ready
sleep 3 && curl -s http://localhost:3100/metrics | head -5


```

### loki-config.yaml


```
auth_enabled: false

server:
  http_listen_port: 3100
  grpc_listen_port: 9096

common:
  instance_addr: 127.0.0.1
  path_prefix: /tmp/loki
  storage:
    filesystem:
      chunks_directory: /tmp/loki/chunks
      rules_directory: /tmp/loki/rules
  replication_factor: 1
  ring:
    kvstore:
      store: inmemory

query_range:
  results_cache:
    cache:
      embedded_cache:
        enabled: true
        max_size_mb: 100

schema_config:
  configs:
    - from: 2020-10-24
      store: tsdb
      object_store: filesystem
      schema: v13
      index:
        prefix: index_
        period: 24h

ruler:
  alertmanager_url: http://localhost:9093

analytics:
  reporting_enabled: false

```

## install grafana 

```
sudo docker network create monitoring
sudo docker network connect monitoring loki
sudo docker run -d --name grafana --restart=always --network monitoring -p 3000:3000 grafana/grafana:latest

sudo docker ps --filter name=grafana && echo -e "\n--- Network Inspection ---" && sudo docker network inspect monitoring --format '{{range .Containers}}{{.Name}}: {{.IPv4Address}}{{"\n"}}{{end}}'
    
sleep 3 && curl -s -o /dev/null -w "HTTP Status: %{http_code}\n" http://localhost:3000

```



Grafana wurde erfolgreich installiert und ist mit Loki verbunden.

**Zugriff:**

- URL: `http://10.10.10.35:3000`
- Standard-Login: `admin` / `admin` (beim ersten Login wird Passwortänderung verlangt)

**Loki-Datenquelle hinzufügen:**

1. Melden Sie sich bei Grafana an
2. Gehen Sie zu: **Configuration → Data Sources → Add data source**
3. Wählen Sie **Loki**
4. URL: `http://loki:3100`
5. Klicken Sie auf **Save & test**

Beide Container befinden sich im `monitoring`-Netzwerk und können über ihre Container-Namen kommunizieren.
