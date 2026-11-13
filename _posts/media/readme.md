# Medien: Screenshots und Videos

Alle Dateien in diesem Ordner werden automatisch aus Playwright-E2E-Läufen erzeugt
([e2e/media/](../../e2e/media/)) und können jederzeit neu generiert werden:

```bash
npm run media   # playwright test -c playwright.media.config.ts  (~6–7 min)
```

Der normale Testlauf `npm run test:e2e` ignoriert `e2e/media/`.

## Videos (`videos/`, WebM, 1440×900, deutsche Untertitel)

| Datei | Inhalt | Spec |
| --- | --- | --- |
| [editing-best-practice.webm](videos/editing-best-practice.webm) | Modellieren nach Best Practice: Ereignisse als Zustand, Aufgaben „Objekt + Verb“, Gateway als Frage, beschriftete Ausgänge, benannte Endzustände, Aufgabe vergrößern, Pool + Lanes, Prüfen per Replay, Speichern | [video-editing.spec.ts](../../e2e/media/video-editing.spec.ts) |
| [token-simulation.webm](videos/token-simulation.webm) | Replay mit XOR-Entscheidung (Play und Step), AND-Split/Join, animierte bpmn-js-Token-Simulation mit gesetztem Gateway-Pfad, „Ein Fall“ aus der Simulationsansicht | [video-token-simulation.spec.ts](../../e2e/media/video-token-simulation.spec.ts) |
| [calculation-simulation.webm](videos/calculation-simulation.webm) | Kalkulations-Simulation am Hochschul-Bewerbungsprozess: Szenario 1 und Szenario 2 mit eigenen Werten, Ergebnisvergleich, Excel-Export | [video-calculation-simulation.spec.ts](../../e2e/media/video-calculation-simulation.spec.ts) |

### Werte der Kalkulations-Simulation

Modell: [04-lanes-university.bpmn](../../e2e/fixtures/examples/04-lanes-university.bpmn).
Szenario 2 entsteht mit „+“ als Kopie von Szenario 1; nur die markierten Werte ändern sich.
Quelle der Werte: [scenarios.ts](../../e2e/media/scenarios.ts).

| Parameter | Szenario 1 | Szenario 2 |
| --- | --- | --- |
| Fälle / Intervall | 100, alle 10 min | 100, alle 10 min |
| Gateway „Unterlagen vollständig?“ | 80 % ja / 20 % nein | 80 % ja / 20 % nein |
| Unterlagen prüfen | 25 min, 5 € | **15 min**, 5 € |
| Unterlagen nachfordern | 10 min, 3 € | 10 min, 3 € |
| Bewerbung bewerten | 10 min, 8 € | 10 min, 8 € |
| Bescheid versenden | 5 min, 2 € | 5 min, 2 € |
| Verwaltung | 1 Person, 40 h/Woche, 30 €/h | **2 Personen, 80 h/Woche**, 30 €/h |
| Prüfungsausschuss | 2 Personen, 80 h/Woche, 50 €/h | 2 Personen, 80 h/Woche, 50 €/h |

Die Simulation zieht bei jedem Lauf einen neuen Zufalls-Seed; die Kennzahlen im Video
schwanken daher leicht zwischen Generierungen. Die Spec prüft, dass Szenario 2 eine kürzere
Ø Durchlaufzeit **und** geringere Kosten als Szenario 1 hat. In beiden Szenarien bleibt
„Verwaltung“ der Engpass.

## Screenshots (`screenshots/`, PNG, 1440×900)

Erzeugt von [screenshots.spec.ts](../../e2e/media/screenshots.spec.ts).

| Datei | Inhalt |
| --- | --- |
| 01-editor-starter | Editor mit Startdiagramm |
| 02-editor-context-pad | Kontextmenü einer Aufgabe |
| 03-example-linear | Beispiel: linearer Ablauf ([01-linear.bpmn](../../e2e/fixtures/examples/01-linear.bpmn)) |
| 04-example-xor-decision | Beispiel: XOR-Entscheidung ([02-xor-decision.bpmn](../../e2e/fixtures/examples/02-xor-decision.bpmn)) |
| 05-example-parallel | Beispiel: AND-Split/Join ([03-parallel.bpmn](../../e2e/fixtures/examples/03-parallel.bpmn)) |
| 06-example-lanes-university | Beispiel: Hochschul-Bewerbung mit Lanes ([04-lanes-university.bpmn](../../e2e/fixtures/examples/04-lanes-university.bpmn)) |
| 07-example-lanes-simple | Beispiel: zwei Lanes ([lanes.bpmn](../../e2e/fixtures/lanes.bpmn)) |
| 08-example-collaboration | Beispiel: Kollaboration Anfrage/Antwort ([diag_req_resp.bpmn](../../testdata/diag_req_resp.bpmn)) |
| 09-replay-token | Replay: roter Token unterwegs |
| 10-replay-branch-choice | Replay: Pfadwahl am XOR-Gateway |
| 11-replay-parallel-split | Replay: zwei Token nach AND-Split |
| 12-token-simulation-mode | bpmn-js-Token-Simulation aktiviert |
| 13-token-simulation-running | bpmn-js-Token-Simulation läuft |
| 14-simulation-view | Simulationsansicht (Sidebar, Szenarien) |
| 15–18-config-* | Konfiguration Szenario 1: Kosten, Dauer, Häufigkeit, Ressourcen |
| 19-szenario1-results | Ergebnis Szenario 1 mit Engpass-Markierung |
| 20-szenario2-config-ressourcen | Ressourcen Szenario 2 |
| 21-szenario2-results | Ergebnis Szenario 2 |

## Hinweise

- Videos nur als WebM (Playwright-Aufnahme, kein ffmpeg nötig). Der Mauszeiger und die
  Untertitel werden nur für die Aufnahme eingeblendet ([helpers.ts](../../e2e/media/helpers.ts)).
- Der native „Speichern unter“-Dialog lässt sich nicht aufnehmen und wird im Editing-Video
  simuliert. Die Spec prüft das gespeicherte XML.
- Remote-Logging (Loki) wird während der Aufnahmen blockiert.
