---
title: Wort-Attacke - Lernspiel
tags:
  - Diy
  - trainer
  - WebApp
  - school
date: 2026-11-09
toc: true
toc_sticky: true
---

# Vom Vokabelfoto zum Monsterkampf: Wie Wort-Attacke mit GitHub Copilot entstand

  

*Eine Projektgeschichte aus sieben Chat-Sitzungen vom 7. bis 9. November 2026.*

  

Am Anfang steht kein fertiges Spielekonzept. Kein ausgearbeitetes Pflichtenheft, keine große Architektur. Am Anfang stehen neun Bilder mit Vokabeln und ein ziemlich praktischer Auftrag:

  

> „lese alle bilder aus den ordner A und erstelle eine tabelle in md für alle vokabeln“

![](../_asset/2026-11-09-wort-attacke-1794242829658.webp)


Aus diesen Bildern wird eine Markdown-Tabelle. Aus der Tabelle wird eine Idee. Und aus vielen kleinen Gesprächen mit GitHub Copilot in VS Code entsteht **Wort-Attacke**: ein Vokabelspiel, in dem richtige Antworten Zauber auslösen, Monster Energie verlieren und aus Lernfortschritt neue Ausrüstung wird.

![](../_asset/2026-11-09-wort-attacke-1794242880390.webp)


Die eigentliche Geschichte steckt dabei nicht nur im fertigen Spiel. Sie steckt in den Korrekturen: Das Monster soll größer sein. Das Handy muss auch hochkant funktionieren. Eine richtige Übersetzung reicht. Und warum kommen eigentlich noch keine Logs an?

  

## Erst die Wörter, dann die Welt

  

Nach dem Übertragen der Fotos folgt die entscheidende Frage: Wie wird daraus ein Lernspiel, das Spaß macht?

  

Die Vorgabe ist eine Zielgruppe ungefähr auf dem Niveau der fünften Klasse. Ein bisschen gruselig darf es werden, aber unterhaltsam statt abschreckend. Copilot schlägt zunächst eine Geisterschule mit benannten Figuren und unterschiedlichen Aktivitäten vor.

  

Doch die Richtung wird im Gespräch konkreter: Oben steht ein Wort, darunter wird die Übersetzung eingegeben. Eine richtige Antwort bringt Punkte und löst eine möglichst coole Attacke gegen einen Boss aus.

  

Auch die erste Bildwelt bleibt nicht unangetastet. Ein „Kühlschrankgeist“ passt nicht zur Vorstellung. Gewünscht ist stattdessen ein großes, namenloses Monster draußen in einer Landschaft.

  

Damit bekommt das Projekt seinen Kern: **Die Vokabel ist nicht vom Spiel getrennt. Ihre richtige Übersetzung ist die Spielhandlung.**

  

Zwischenzeitlich fällt die Frage nach einem „gemini notebook“ fürs Handy. Das tatsächlich entstandene Ergebnis ist eine installierbare Web-App mit Offline-Unterstützung. Für das Spielen auf dem Telefon braucht es damit kein Notebook als Bedienoberfläche.

  

## Aus einer Wissenslücke wird ein Heiltrank

  

Ein Spiel, das nur richtige Antworten feiert, wäre schnell frustrierend. Deshalb kommt früh eine zweite Mechanik hinzu: **Überspringen**.

  

Wer ein Wort nicht weiß, kann sich die Lösung anzeigen lassen. Das Monster greift an, die Spielerenergie sinkt, und die Frage kommt später wieder. Wird sie dann richtig beantwortet, gibt es einen Heiltrank.

![](../_asset/2026-11-09-wort-attacke-1794242922591.webp)

Das ist mehr als ein zusätzlicher Button. Es verbindet Wiederholung mit einer sichtbaren Belohnung: Gerade das Wort, das zunächst nicht geklappt hat, kann später helfen, weiterzuspielen.

  

Auch diese Regel entwickelt sich weiter. Zunächst ist ein einzelner Trank pro Kampf vorgesehen. In einer späteren Sitzung wird daraus ein Vorrat: Mehrere zunächst falsch und danach richtig beantwortete Fragen können mehrere Tränke einbringen. Die Anzahl erscheint direkt am Symbol, Tränke werden einzeln verbraucht und bleiben gespeichert.

  

Die Spielidee entsteht hier nicht in einem einzigen perfekten Prompt. Sie wird beim Ausprobieren genauer.

  

## Das Handy ist kein kleiner Desktop

  

Eine der hartnäckigsten Aufgaben ist die Darstellung.

  

Das Monster soll gut sichtbar sein, aber die Fragekarte darf es nicht verdecken. Gleichzeitig müssen Eingabefeld, Angriff, Überspringen, Punkte, Leben und Heiltrank erreichbar bleiben.

  

Eine frühe Browserprüfung im Querformat zeigt das Problem sehr konkret: Bei einem Sichtbereich von **844 × 390 Pixeln** ist das Dokument zunächst **560 Pixel hoch**. Heiltrank und Monsterenergie liegen außerhalb des sichtbaren Bereichs. Keine Fehlermeldung in der Konsole – und trotzdem kein brauchbares Ergebnis.

![](../_asset/2026-11-09-wort-attacke-1794243012147.webp)


Nach der Korrektur entspricht die Dokumenthöhe den 390 Pixeln des Displays. Die Bedienelemente sind erreichbar und das Monster bleibt prominent sichtbar.

  

Zunächst wird auf dem Handy-Hochformat noch zum Drehen aufgefordert. Die nächste Sitzung trägt schon im Titel den Änderungswunsch: „hochant mobile display test“. Nun soll das Spiel auch ohne Drehen funktionieren. Laut damaligem Testbericht gelingen Laden, Eingabe und Angriff bei **390 × 844** und **360 × 800 Pixeln** ohne horizontalen Überlauf.

  

Später folgen weitere Details: Buttons dürfen nicht aus der Fragekarte ragen. Punkte, Münzen, Serie und Leben müssen auch auf schmalen Displays sichtbar bleiben.

  

Die Lektion daraus ist angenehm handfest: „Responsiv“ ist erst dann etwas wert, wenn die wichtigen Handlungen auf dem tatsächlichen Bildschirm funktionieren.

  

## Ein Magier, der nicht von der Stange kommt

  

Mit dem Shop erhält das Lernen eine zweite Belohnungsebene. Richtige Antworten bringen Münzen, besiegte Monster einen Bonus. Davon lassen sich Gewänder und Hüte kaufen; die Hautfarbe bleibt kostenlos wählbar.

![](../_asset/2026-11-09-wort-attacke-1794243049289.webp)


Dann kommen eigene Bildvorlagen ins Spiel. Ein Magier aus einem vorhandenen Bild wird freigestellt und als **Lila Sternenmagier** angeboten. Sein Preis wird im nächsten Schritt auf **3.000 Münzen** festgelegt. Auch die Grafik wird nachgebessert: weichere Kanten, keine störende weiße Fläche zwischen Körper und Stab.

  

Besonders greifbar wird die Gestaltung beim Schwert aus der Vorlage „Schwert Arnos Spiel“. Es wird für die Spielfigur vorbereitet und als **Arnos Wort-Attacke-Schwert** in den Shop aufgenommen.

 ![](../_asset/2026-11-09-wort-attacke-1794243076540.webp)
  

Dafür muss die Figur mehr können als nur ein komplettes Bild austauschen. Der Magier bekommt getrennte Bereiche für Kopf, Hut, Gewand und beide Hände. Seine linke Hand trägt immer den langen Zauberstab; rechts kann ein zusätzlicher Gegenstand ausgerüstet werden. Hut und Gewand des Sternenmagiers werden kombinierbar.

  

Die Gegenstände bleiben rein optisch. Sie verändern den Auftritt, nicht die Kampfstärke.

  

Auch das Monster bekommt Aufmerksamkeit: unterschiedliche Erscheinungsbilder, wechselnde Münder und Ohren, passend sitzende Zähne. Selbst die Reihenfolge eines Treffers wird präzisiert:

  

**Der Magier schießt. Der Zauber trifft. Erst dann sinkt die Monsterenergie und die Prozentanzeige leuchtet auf.**

  

Solche Details lassen eine richtige Antwort nicht nur korrekt, sondern wirksam erscheinen.

  

## Latein braucht andere Fragen

  

Am 8. November erweitert sich der Horizont: Neben Englisch soll Latein auswählbar sein. Eine Startseite mit zwei Sprachbuttons kommt hinzu; der Shop bleibt an vertrauter Position.

  

Latein lässt sich allerdings nicht einfach als zweite Wortliste behandeln. Die Vorgabe ist ausdrücklich anders: Das lateinische Wort wird angezeigt, die Formen müssen vollständig eingegeben werden, und bei der deutschen Bedeutung genügt eine gültige Übersetzung.

![](../_asset/2026-11-09-wort-attacke-1794243127083.webp)

  

Die gemeinsame Spielwelt bleibt erhalten. Punkte, Münzen und Ausrüstung werden gemeinsam verwendet, die Lernstände der Sprachen getrennt geführt. Lateinische Längenzeichen sind bei der Eingabe optional.

  

Am 9. November folgen weitere Fotos mit **48 Vokabeln für die Abschnitte 11.1 bis 11.4**. Anschließend wird die Eingabe selbst zum Thema: Klammerzusätze und Auslassungspunkte aus einer Buchvorlage eignen sich schlecht als erwartete Antwort.

  

Ein wiederverwendbares Python-Skript bereinigt deshalb die deutsche Tabellenspalte. Ausgeführt wird es auf ausdrücklichen Wunsch mit `uv`. Die anderen Spalten bleiben unverändert.

  

Danach kommt die Lektionsauswahl hinzu: Nach der Sprache können einzelne, mehrere oder alle Lektionen gewählt werden. Ihre Namen stammen aus den Überschriften der Markdown-Dateien.

  

Aus Fotos werden so nicht nur digitale Wörter, sondern auswählbare Lernportionen.

  

## Das Spiel soll sich erinnern

  

Mit wachsendem Umfang entsteht ein neues Bedürfnis: Nicht jedes Mal von vorn anfangen.

  

Eine einfache Spitznameneingabe wird zum lokalen Spielerprofil. Punkte, Münzen, Ausrüstung und Lernfortschritt werden pro Profil gespeichert, ebenso die letzte Sprache und die Lektionsauswahl.

![](../_asset/2026-11-09-wort-attacke-1794243156534.webp)


Aber auch eine gut gemeinte Eingabe kann im Weg stehen. Deshalb folgt gleich die nächste Verfeinerung: Der Spitzname soll nur beim ersten Einstieg abgefragt werden. Wer keinen angeben möchte, kann überspringen und als Gast spielen. Später lässt sich das Profil bewusst wechseln.

  

Dabei bleibt die Grenze klar: Es handelt sich um lokale Browserprofile, nicht um Benutzerkonten mit Passwort oder geräteübergreifender Synchronisierung.

  

## Wenn „rufen; nennen“ trotzdem nicht funktioniert

  

Eine besonders aufschlussreiche Schleife entsteht bei mehreren deutschen Bedeutungen.

  

Für einen Eintrag wie `alle; alle zusammen` soll eine einzelne Bedeutung genauso richtig sein wie beide zusammen – unabhängig von ihrer Reihenfolge. Jede eingegebene Bedeutung muss allerdings gültig sein.

  

Die Anpassung wird umgesetzt und getestet. Dann kommt die Rückmeldung:

  

> „klapp noch nicht“

  

Das konkrete Beispiel lautet `vocāre` mit den Bedeutungen `rufen; nennen; bezeichnen als`.

  

Nun reicht die Aussage „Die Tests sind grün“ nicht mehr. Die Eingaben werden im tatsächlichen Browserformular geprüft. Zwei Bedeutungen funktionieren, drei ebenfalls, auch in umgekehrter Reihenfolge. Für das Beispiel werden zusätzlich alle **15 nichtleeren, geordneten Kombinationen ohne Wiederholung** als Regressionstest abgedeckt.

  

Bei der Untersuchung zeigt sich außerdem eine alte Cache-Version im bisherigen lokalen Testbrowser: **v10 statt v29**.

  

Das macht den Fall so lehrreich. Richtiger Quellcode, laufender Server und die tatsächlich geladene App sind nicht automatisch derselbe Stand. Gerade bei einer offlinefähigen Web-App gehört der Cache zur Fehlersuche dazu.

  

## Der letzte Gegner heißt Deployment

  

Die jüngste Entwicklungssitzung ergänzt Ereignisprotokolle für Loki. Profilöffnung, Kampfstarts, Siege und Antwortergebnisse sollen sichtbar werden. Eingegebene Antworten werden nicht mitgesendet; ein Hinweis auf der Startseite informiert über die Übertragung.

  

Die Tests bestehen. Die CORS-Vorprüfung funktioniert. Dann folgt wieder eine Rückmeldung aus der Praxis: Es seien noch keine Daten angekommen.

  

Die Untersuchung trennt diesmal zwei Fragen: Kann Loki Daten annehmen? Und enthält die veröffentlichte App überhaupt schon den Logger?

  

Ein Push mit synthetischen Testdaten wird mit **HTTP 204** angenommen. Der Endpunkt ist erreichbar. Die veröffentlichte App enthält zu diesem Zeitpunkt aber noch nicht die lokale Logger-Erweiterung.

  

Der Fehler liegt also nicht dort, wo man zuerst suchen könnte. Und die Diagnose führt nicht automatisch zu einem ungefragten Commit oder Push.

  

Auch das gehört zur Zusammenarbeit mit einem Coding-Assistenten: Änderungen schreiben, Tests ausführen, Daten senden und veröffentlichen sind unterschiedliche Schritte.

  

## Was aus sieben Chats bleibt

  

Wort-Attacke ist nicht durch einen einzigen Auftrag „Baue mir ein Spiel“ entstanden. Das Projekt wächst durch kurze, konkrete Rückmeldungen:

  

Das Monster gehört in die Landschaft. Das Eingabefeld muss in der Karte bleiben. Eine Bedeutung reicht. Der Heiltrank braucht einen Zähler. Die letzte Auswahl soll erhalten bleiben.

  

Copilot überträgt Inhalte, entwirft, implementiert und prüft. Die Richtung entsteht im Dialog – und wird immer wieder an der tatsächlichen Nutzung korrigiert.

  

Aus neun Vokabelfotos wird eine kleine Spielwelt mit Zaubern, Ausrüstung, zwei Sprachen und lokalen Profilen. Ihr schönster Gedanke steckt noch immer in der frühen Heiltrank-Regel:

  

**Was zuerst nicht gelingt, ist nicht verloren. Es kommt wieder – und kann beim nächsten Mal neue Energie geben.**

  

---

  

## Quellen und Einordnung

  

Diese Story verdichtet alle sieben im Screenshot genannten Projektsitzungen. Die vier älteren Verläufe wurden aus den zugehörigen lokalen Copilot-SDK-Sitzungsdateien gelesen, die drei jüngeren über die Sitzungsschnittstelle. Der aktuelle Projektstand und die [README](../README.md) dienten zum Abgleich. Diese achte Sitzung erstellt die Story selbst.

  

| Sitzung                            | Beginn     | Beitrag zur Geschichte                                                           |
| ---------------------------------- | ---------- | -------------------------------------------------------------------------------- |
| Bilder aus Ordner A in md-Tabelle  | 07.11.2026 | Neun Fotos, Spielidee, Monsterkampf, Überspringen, erste mobile Prüfungen        |
| hochant mobile display test        | 07.11.2026 | Hochformat, alternative Antworten, Trankzähler und mehrere Heiltränke            |
| Shop für magische Anziehsachen     | 07.11.2026 | Shop, Bildvorlagen, Ausrüstung, Monsterdetails und weitere Eingabeverbesserungen |
| Startseite für Lernspiel erstellen | 08.11.2026 | Sprachwahl, Lateinmodus und gemeinsame Spielwelt                                 |
| Latein Vokabeln aus Bildern        | 09.11.2026 | Weitere Vokabeln, Bereinigungsskript, Lektionsauswahl und Profile                |
| deutsche Eingaben für md Eintrag   | 09.11.2026 | Mehrere Bedeutungen, konkreter Browsernachtest und Cache-Diagnose                |
| log data to Loki endpoint          | 09.11.2026 | Ereignisprotokollierung, synthetischer Test-Push und Veröffentlichungsdiagnose   |


___

## Weiteres 

![](../_asset/2026-11-09-wort-attacke-1794243257717.webp)



  
![](../_asset/2026-11-09-wort-attacke-1794243275628.webp)

![](../_asset/2026-11-09-wort-attacke-1794243294347.webp)
