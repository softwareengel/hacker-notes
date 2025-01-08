---
title: 
tags: 
date: 2025-01-08
toc: true
toc_sticky: true
---

# 

``` Mermaid 
classDiagram
    note "Von Biblothek zu Seite "
Buch --|> Sachbuch 
Regal "1"--"*" Buch
Biblothek "1"--"*" Regal
Buch "1"-- "*" Seite 
class Buch {
- String titel 
}
class Regal{
- String nummer
}
class Biblothek {
- String Name
}
class Sachbuch {
- String sachbereich
}
class Seite
```



![](../_asset/2025-01-08-obsidian-mermaid-20250108091512.jpg)


![](../_asset/2025-01-08-obsidian-mermaid-20250108091632.jpg)



![](../_asset/2025-01-08-obsidian-mermaid-20250108091836.jpg)


![](../_asset/2025-01-08-obsidian-mermaid-20250108091935.jpg)



![Drawing 2025-01-08 09.14.31.excalidraw](../Excalidraw/Drawing%202025-01-08%2009.14.31.excalidraw.png)
