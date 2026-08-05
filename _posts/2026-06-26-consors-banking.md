---
title: consors-banking-solved -
tags:
date: 2026-06-26
toc: true
toc_sticky: true
---

# Ist das schlecht gemacht !

https://chatgpt.com/share/6a3e5539-17b0-83eb-986a-2e7e32b3b07b

## TLDR: Die 9 Stellige Tan ist nun in der Consors App im Profil versteckt, die ConsorsSecure App 8-Stellen TAN funktioniert nicht mehr. 


## chat Log 

analysiere jameica banking konto zugang consors , aktuelle problem ?

Ich prüfe das als aktuelles FinTS/HBCI-Problem rund um Jameica/Hibiscus und Consorsbank. Ich suche nach Störungsmeldungen, bekannten Plugin-/Banking4W-/Hibiscus-Hinweisen und typischen Fehlermeldungen, damit wir Ursache und nächste Schritte trennen können.

Nachgedacht für 51s

### Einschätzung: sehr wahrscheinlich **kein allgemeiner Consors-Ausfall**, sondern TAN-/Zugangs-Umstellung

Stand **26. Juni 2026**: Öffentlich gibt es keinen klaren Hinweis auf eine flächige Consorsbank-Störung; Downdetector/Allestörungen meldet aktuell „no current problems“.  
Das aktuelle Muster passt viel eher zur **Ablösung der SecurePlus App** und zur Umstellung auf die **Consorsbank App** für FinTS/HBCI/Jameica/Hibiscus.

Consorsbank schreibt selbst: Die **SecurePlus App wurde Ende April 2026 abgelöst**; statt SecurePlus braucht man die **Consorsbank App** für Login und Freigaben. Noch wichtiger: Die App kann **nur noch bis Ende Juni 2026** mithilfe der SecurePlus App aktiviert werden; danach braucht man einen Aktivierungscode per Brief.

### Wahrscheinlichste Ursache in Jameica/Hibiscus

In Hibiscus ist vermutlich noch ein alter Bankzugang, ein altes TAN-Verfahren oder alte Bankparameter gespeichert. Andere Banking-Software meldet genau zu Consorsbank aktuell Fehler wie:

„Nachricht teilweise fehlerhaft“, „Dialogbearbeitung abgebrochen“, „Fehler bei der Dialoginitialisierung“ mit BLZ **76030080**; StarMoney nennt als Lösung den Wechsel auf **„Consorsbank/myPrivateBank App (901)”**.

Für Jameica/Hibiscus heißt das sinngemäß:

1. **Consorsbank App aktivieren** und prüfen, ob Login im Web funktioniert.
2. In Hibiscus unter **Hibiscus → Bank-Zugänge → PIN/TAN → Consors-Zugang** den Bankzugang **synchronisieren / Konfiguration testen**.
3. Falls die TAN-Auswahl nicht neu erscheint: im Bankzugang **„TAN-Verfahren zurücksetzen“** und dann erneut synchronisieren. Hibiscus zeigt die TAN-Auswahl sonst ggf. nicht mehr an, wenn die Auswahl früher gespeichert wurde.
4. Als TAN-Verfahren **Consorsbank App / myPrivateBank App (901)** wählen.
5. Falls „TAN ungültig“ kommt: TAN nicht mehr aus der SecurePlus App erzeugen. In der Consorsbank App: **Login → Profil → TAN**. Outbank dokumentiert denselben Consors-Fehler so: SecurePlus-TANs werden seit Ende April 2026 nicht mehr akzeptiert.

### Zugangsdaten prüfen

Consorsbank verlangt für FinTS/HBCI Plus **FinTS ab Version 4.0**. Die Nutzerkennung ist die **Kontonummer plus dreistellige Berechtigtennummer**, z. B. Kontonummer + `001`; als Bankserver nennt Consorsbank:

```
brokerage-hbci.consorsbank.de/hbci
```

Bei der ersten Einrichtung soll man Girokonto oder Verrechnungskonto verwenden; weitere Konten/Depots werden danach automatisch übertragen.

### Zusätzlicher Punkt: Überweisung vs. Echtzeitüberweisung

Falls der Abruf klappt, aber eine Überweisung scheitert mit etwa:

```
Geschäftsvorfall InstUebSEPA wird nicht unterstützt
```

dann in Hibiscus beim Auftragstyp **nicht Echtzeitüberweisung**, sondern normale **SEPA-Überweisung** wählen. Consors unterstützt laut eigener HBCI-FAQ Salden, Umsätze, SEPA-Einzelüberweisungen und Depotbestände, aber keine erweiterten Funktionen wie Terminüberweisungen; Outbank nennt ebenfalls, dass geplante Zahlungen, Daueraufträge und Instant Payments über HBCI/FinTS aktuell nicht verfügbar sind.

### Kurzdiagnose

**Am wahrscheinlichsten:** alter SecurePlus-/TAN-Status in Hibiscus.  
**Fix:** Consorsbank App aktivieren → Hibiscus Bankzugang synchronisieren → TAN-Verfahren zurücksetzen → **App (901)** wählen → PIN/TAN neu eingeben.  
**Nicht vergessen:** Bis **Ende Juni 2026** ist die Aktivierung der Consorsbank App mit SecurePlus noch einfacher möglich; danach wird ein Aktivierungscode-Brief nötig.

Eingefügter Text(1).txt

Dokument

Der Log bestätigt die Vermutung schon ziemlich klar: Hibiscus bietet beide Verfahren an, aber du hast **900 SecurePlus TAN Generator** ausgewählt; danach signiert Hibiscus auch mit `secfunc 900`. Das ist vermutlich der Knackpunkt.

Nachgedacht für 10s

Ja — der Log zeigt das Problem ziemlich eindeutig:

**Du hast in Hibiscus das falsche TAN-Verfahren gewählt: `900 SecurePlus TAN Generator`.**  
Consors bietet zwar beide Verfahren an, aber Hibiscus speichert danach ausdrücklich:

```
selected pintan method by user: 900saving current tan method: 900setting secfunc to 900
```

Im Log sieht man außerdem, dass Consors/Hibiscus beide Verfahren anbietet:

```
900: SecurePlus TAN Generator901: Consorsbank/myPrivateBank App
```

und dass Hibiscus später tatsächlich mit `secfunc=900` arbeitet.

### Was du tun solltest

In Hibiscus/Jameica:

1. **Bank-Zugänge** öffnen.
2. Den Consorsbank PIN/TAN-Zugang bearbeiten.
3. **TAN-Verfahren zurücksetzen** oder Bankzugang erneut synchronisieren.
4. Wenn die Auswahl kommt, **nicht 900**, sondern wählen:

```
901 Consorsbank/myPrivateBank App
```

5. Danach erneut synchronisieren.

### Wichtig

Der Bankserver, BLZ und HBCI-Grunddaten sehen im Log korrekt aus:

```
brokerage-hbci.consorsbank.de/hbciBLZ 76030080HBCI version 300
```

Das ist also wahrscheinlich **kein URL-/BLZ-/PIN-Problem**, sondern die falsche TAN-Methode.

### Falls 901 nicht funktioniert

Dann zuerst prüfen, ob die **neue Consorsbank App** vollständig aktiviert ist und du dort TAN/Freigaben erzeugen kannst. Danach in Hibiscus nochmal BPD/UPD löschen bzw. Bankzugang synchronisieren und erneut **901** auswählen.

Eingefügter Text(2).txt

Dokument

Eingefügter Text(3).txt

Dokument

![grafik(14).png](https://chatgpt.com/backend-api/estuary/content?id=file_00000000a74471f5abf7dc6bde9dacb3&ts=495129&p=fs&cid=1&sig=934d177ab0554eedd3388b9445a5d53489ddd48f02acc4acbaa0726883d9aa13&v=0)

![grafik(15).png](https://chatgpt.com/backend-api/estuary/content?id=file_00000000b10c720c929ba919eb4b5a09&ts=495130&p=fs&cid=1&sig=a1d5da27f9e81611d93a1df08ea638079611b5138881597c4ea3367fad969c5b&v=0)

![grafik(16).png](https://chatgpt.com/backend-api/estuary/content?id=file_0000000065fc71f5b1556b0aea82aae9&ts=495130&p=fs&cid=1&sig=e942f0928fe5c6b5e1f376fc15c3861944197b32d6968ee68384826c599c9bb4&v=0)

danach in Consorsbank App, aber freigabe für hibiskus fints banking nicht möglich ,

Nachgedacht für 31s

Du bist jetzt **in der richtigen Consorsbank App** und sie ist offenbar grundsätzlich aktiv, weil die Tagesgeldkonten angezeigt werden. Das Problem ist also nicht mehr „falsche App“, sondern: **die FinTS/Hibiscus-Freigabe erscheint in der App nicht sichtbar**.

Consors beschreibt: Für Website-Login und Auftragsfreigaben wird seit der SecurePlus-Ablösung die **Consorsbank App** verwendet; bei erlaubten Pushs soll man auf die Push-Mitteilung tippen, ohne Push die App öffnen und dort die Freigabe bestätigen.

### Was du jetzt genau probieren solltest

1. In Hibiscus den Vorgang starten, bis der **TAN-Eingabe/Freigabe-Dialog** erscheint.
2. **Nicht sofort OK klicken.**
3. Am Handy die Consorsbank App öffnen.
4. Auf der **Home-Seite nach oben/mitte schauen**, besonders **oberhalb des ersten Kontos**. Laut einem aktuellen Hibiscus-Forumseintrag erscheint die Consors-Freigabe teils nicht als echte Push-Nachricht, sondern nur als unauffälliger Hinweis in der App mit einem Button wie **„Fortfahren“**.
5. In der App bestätigen.
6. Erst danach in Hibiscus auf **OK** klicken.

Auf deinem Screenshot sehe ich **keinen sichtbaren Freigabe-Hinweis**. Normalerweise müsste dort zusätzlich ein Banner oder Button zur Freigabe auftauchen.

### Prüfe in der App

Gehe in der Consorsbank App zu:

```
Profil → Einstellungen → Benachrichtigungen
```

und aktiviere Push-Benachrichtigungen. Consors nennt diesen Pfad selbst für Freigaben über die App.

Danach zusätzlich prüfen:

```
Profil → Einstellungen → Sicherheit & Datenschutz → verbundene Geräte
```

Falls zu viele oder alte Gerätebindungen vorhanden sind, kann das stören; Consors nennt maximal **3 Gerätebindungen**.

### Gegenprobe: Web-Login testen

Bitte teste einmal unabhängig von Hibiscus:

1. Am PC bei Consorsbank im Web einloggen.
2. Schauen, ob in der App eine Login-Freigabe erscheint.
3. Diese bestätigen.

Wenn **auch beim Web-Login keine Freigabe erscheint**, ist die App/Gerätebindung/Freigabefunktion bei Consors noch nicht sauber aktiv. Dann App aktualisieren, Uhrzeit/Internet prüfen und ggf. Gerätebindung neu aktivieren; Consors nennt bei TAN-/App-Problemen unter anderem falsche Uhrzeit, instabile Verbindung oder veraltete App-Version als Ursachen.

Wenn **Web-Login funktioniert, aber Hibiscus nicht**, dann ist es sehr wahrscheinlich genau das aktuelle Consors-FinTS/PushTAN-Problem: Hibiscus verwendet korrekt `901`, aber Consors liefert die Freigabe nicht sichtbar oder nicht zuverlässig in die App. Dein Log zeigt ja bereits, dass Hibiscus nun richtig auf `901` / Consorsbank-App umgestellt wurde.

### Manuelle TAN nur als Notlösung

Falls Hibiscus doch ein Eingabefeld für eine TAN zeigt: In der App unter **Profil → TAN** schauen. StarMoney dokumentiert für Consors ebenfalls diesen Weg zum TAN-Bereich in der Consorsbank/myPrivateBank App.

Bei deinem gezeigten Hibiscus-Fenster sah es aber eher nach **App-Freigabe ohne TAN-Eingabe** aus. Dann ist der entscheidende Schritt: Freigabe in der App finden, bestätigen, dann OK in Hibiscus.

![grafik(17).png](https://chatgpt.com/backend-api/estuary/content?id=file_00000000d440722fb489ea9aa5676aed&ts=495130&p=fs&cid=1&sig=c5aaf184c38df6cf6e0f063439ded4d8cf7f409958014b2eab02afdc9206b816&v=0)

nope danach kommt das: und bei Consorsbank/myPrivateBank App kann ich mich nicht anmelden

Nachgedacht für 1m 48s

Genau: **bei „Consorsbank/myPrivateBank App“ musst du dich nicht in der myPrivateBank App anmelden.**  
Für dein Konto ist die **Consorsbank App** richtig. Die myPrivateBank App ist für BNP Paribas Wealth Management/Private-Banking; selbst deren Seite sagt, dass man bei vorhandener Consorsbank App nicht wechseln muss und Aufträge/Login über die Consorsbank App freigeben kann.

Der Name in Hibiscus ist nur der technische FinTS-Name:

```
Consorsbank/myPrivateBank App
```

### Was dein Hibiscus-Dialog bedeutet

Der Dialog ist widersprüchlich: Er sagt „TAN generieren und hier eingeben“, zeigt aber **kein Eingabefeld**. Dein Log passt dazu: Hibiscus hat `901` korrekt gewählt, erkennt das Verfahren als **Decoupled**, öffnet einen `pushtan 2.0 dialog`, wartet dann, und bricht nach etwa einer Minute mit „Fehler beim Aktualisieren der UPD“ ab.

Das heißt: Hibiscus wartet offenbar auf eine App-Freigabe, aber in der Consorsbank App erscheint keine Freigabe.

### Nächster sinnvoller Test

In der **Consorsbank App**, nicht myPrivateBank:

```
Profil → TAN
```

Consors beschreibt genau diesen Weg: Im Profil auf **TAN** tippen; dann wird eine **9-stellige TAN** angezeigt.  
Consors schreibt außerdem: Wenn keine Push-Freigabe kommt, App öffnen, zu **Profil → TAN** gehen, TAN erzeugen und diese beim Auftrag eingeben.

Problem: Dein Hibiscus-Fenster hat kein sichtbares Eingabefeld. Probiere deshalb einmal:

1. Hibiscus-Dialog größer ziehen.
2. Mit **Tab** durch die Felder springen, ob ein verstecktes TAN-Feld Fokus bekommt.
3. Falls kein Feld kommt: in Consorsbank App unter **Profil → TAN** eine TAN erzeugen, dann in Hibiscus **OK** drücken.

Wenn danach wieder derselbe Fehler kommt, kann Hibiscus die Consors-901-Freigabe aktuell bei dir nicht sauber abschließen.

### Workaround, der einen Versuch wert ist

Ein aktueller Hinweis von ALF-BanCo zur Consors-Umstellung sagt: Verfahren **901** sei manuelle TAN-Eingabe, **902** ohne manuelle TAN-Eingabe; wenn 901 nicht funktioniert, solle man testweise **900** wählen. Wichtig dabei: Die TAN sei trotzdem über die neue Banking-App zu erzeugen und 9-stellig.

Für Hibiscus hieße das als Test:

1. **TAN-Verfahren zurücksetzen**
2. **BPD/UPD löschen**
3. Neu synchronisieren
4. Testweise **900 SecurePlus TAN Generator** wählen
5. TAN trotzdem in der **Consorsbank App → Profil → TAN** erzeugen

Bei dir hatte 900 vorher schon einmal `Synch.TAN2Step6`

.
