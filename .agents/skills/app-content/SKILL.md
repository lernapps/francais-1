---
name: app-content
description: Use for any content work in this app - researching, writing, extending, correcting or reviewing its competencies, chapters, pages, rounds, questions, exercises, figures, terms or sources. This app's own content decisions; they take precedence over the generic lernapps content skills. Load it before you change any content.
---

# Content guide of this app

Explainer "Bonjour, Léa und Malik!" für Französisch, Richtstufe 5/6 (Anfang 1. Lernjahr), eine Einheit-App
(`subject: franzoesisch` in `src/app.yaml`, format 2, `languages: [de]`). Kein `scope` (kein `open-task`, kein Material des
Erstellers). Ton: Ja, mit KI-Stimme, siehe „Exercise patterns“.

## Curriculum

- Land und Schulform unbekannt, Richtstufe 5/6. Orientierung: die Lernlandkarte `https://lernapps.net/apps/map/franzoesisch.json`
  (Reihenfolge nach `requires`, Richtstufe 5-6, Stufe 1 und 2). Der Lehrplan ersetzt das nicht.
- KMK-Bildungsstandards Erste Fremdsprache (2003/2004, i. d. F. 22.06.2023) gelten für Klasse 9/10, nicht für 5/6; geöffnet,
  keine Einheit zitiert.
- Das Material des Erstellers (nicht vorhanden) hätte Vorrang vor der Karte.

## Competencies

Ein Kapitel `kapitel-1` „Bonjour, Léa und Malik!“, sieben Seiten, je eine Kompetenz der Karte (Ids der Karte, Wortlaut nicht ändern).
Datei `src/kapitel-1/<seite>.yaml`; die Seite nennt `competencies: [<id>]`.

| Seite (Datei) | Id der Karte | Strang | Ich kann … |
|---|---|---|---|
| `laut-und-schrift` | `laut-und-schrift` | aussprache | häufige Buchstabenverbindungen richtig aussprechen, z. B. ou, oi, au, eau, ch und gn |
| `begruessen` | `begruessen-und-vorstellen` | wortschatz | mich begrüßen, verabschieden, vorstellen und fragen, wie es jemandem geht |
| `zahlen` | `zahlen-bis-100` | wortschatz | die Zahlen bis 100 verstehen und sagen, auch soixante-dix, quatre-vingts und quatre-vingt-dix |
| `pronomen` | `subjektpronomen` | grammatik | die Subjektpronomen je, tu, il, elle, on, nous, vous, ils und elles verwenden |
| `etre` | `verb-etre` | grammatik | être im Präsens konjugieren und damit Personen und Dinge vorstellen (c’est, il est) |
| `artikel` | `bestimmter-artikel` | grammatik | den bestimmten Artikel le, la, l’ und les richtig vor ein Nomen setzen |
| `avoir` | `verb-avoir` | grammatik | avoir im Präsens konjugieren und Wendungen wie il y a und j’ai 13 ans verwenden |

Reihenfolge der Seiten wie in der Tabelle (`pages` in `chapter.yaml`); jede Voraussetzung (`requires`) steht auf einer früheren Seite,
kein `ahead`, keine Wiederholungsseite. Pro Seite genau eine Kompetenz, genau ein Strang.

## Content structure

- Jede Seite besteht aus `section`-Blöcken mit festen Ids, in dieser Reihenfolge, ein nicht gebrauchter Abschnitt fällt weg:
  1. `einstieg` – „Worum es geht“: Szene (`figure`, `image: images/szene-<seite>.svg`), zwei bis drei Sätze Situation mit Léa und Malik,
     dann Ziel in der Form „Danach kannst du …“ und woran die Seite anknüpft.
  2. `neu` – Titel nach Inhalt („Neu: …“): Tabelle (`table`), kurze Erklärung, jedes neue Wort mit Bedeutung; ein `note` für den häufigsten Fehler.
  3. `nachsprechen` – Titel „Hören und nachsprechen“: ein `speaking-task` mit der Id `sprechen-ueben` (eine Aufgaben-Id darf nicht gleich einer Abschnitts-Id sein; nur Seiten mit Ton).
  4. `uebung` – „Übung“: leicht → schwer: 1 Quizblock (`single-choice` oder `matching`), 2 `language-task` Lücke/Auswahl,
     3 `language-task` mit `audio` (Diktat oder Hören), 4 `language-task` Übersetzen.
- Länge: Erklärung höchstens 6 kurze Sätze, Tabellen höchstens 8 Zeilen, Übung 4 bis 6 Aufgaben mit je 3 bis 8 Items.
- Kapitelseite: Titel „Bonjour, Léa und Malik!“, `summary` in einem Satz. Startseite (`src/app.yaml`): `intro` stellt Léa und Malik vor.
- Geschichte: Léa (11, kurze braune Haare, rote Jacke) lebt in einer kleinen Stadt in Frankreich, Malik (11, schwarze Locken, Brille, blauer
  Rucksack) ist neu in ihrer Klasse; sie sind eine Szene pro Seite: 1 Schultor-Schild, 2 Pausenhof-Gruß, 3 Klassenzimmer
  (Alter, Hausnummer), 4 Fußballtraining, 5 Familienfoto, 6 Schultasche, 7 Léas Zimmer. Nur erfundene Figuren, keine Marken, keine Figuren
  aus Büchern, Filmen oder Spielen.

## Terminology

- Anrede der Kinder: „du“ durchgehend. Kurze Sätze, Sachen aus dem Alltag von Elf- bis Zwölfjährigen.
- Verwendet: „Seite“, „Übung“, „Hören“, „Nachsprechen“, „Merke“ (für `note`), „Wort“, „Verb“, „Artikel“ (die Begriffe der Grammatik erklären, bevor sie gebraucht werden).
- Vermieden: Lautschrift und Fachwörter ohne Erklärung (z. B. „Nasal“, „Liaison“, „Subjekt“) auf diesen Seiten; „Buchstabenverbindung“ und „Laut“ werden auf Seite 1 erklärt. Klangvergleiche (z. B. „ou wie langes u in Mut“) prüft vor der Veröffentlichung jemand mit Französisch-Kenntnissen.
- Wörter: aus dem Grundwortschatz Französisch (Stufe A1, `https://lernapps.net/apps/map/franzoesisch/grundwortschatz/`); ein Wort außerhalb nur,
  wenn die Szene es braucht, und es wird dort mit Bedeutung erklärt. Jedes Wort mit Bedeutung stehen, bevor eine Übung danach fragt.
- Französisch: Akzente und Apostroph wie geschrieben (m’appelle, l’école); im YAML Texte mit `:` oder `'` am Anfang in Anführungszeichen.
- Glossar: Begriffe als `definition`-Block, nur wo gebraucht (z. B. „Artikel“, „Pronomen“), je ein Satz.

## Exercise patterns

- **Wörter einführen** (alle Seiten): `table` mit schmalen Spalten (höchstens drei, kurze Zellen, wegen 360 px), z. B. `header: [Buchstaben, Wort, Bedeutung]`, ein Wort je Zeile; kein Datensatz. Beispiel: `kapitel-1/laut-und-schrift.yaml`, Abschnitt `neu`.
- **Wörter mit Artikel, dann Sätze** (Wunsch des Erstellers nach Hören der Stimmen): Einzelwörter werden mit le/la gesprochen und geschrieben („le chat“), weil die Stimmen Einzelwörter schlecht sprechen; vor Seite 6 sind le/la feste Wendungen (die Seite sagt: „gehört dazu, mehr auf Seite 6“). Zweite Stufe des Nachsprechens: ein kurzer Satz „Voici le chat.“ in einem zweiten `speaking-task` (Id `sprechen-satz`). Ein Einzelwort ohne Artikel wird nicht als Audio erzeugt.
- **Hören und nachsprechen** (Seiten 1 bis 3, dann wo es passt): Block `speaking-task` mit `language: fr`, `items` (1 bis 10) mit `audio: <datei>.mp3`
  und `text`. Kein Prüfen; die Kinder bewerten sich selbst. Kann nicht in die Selbsteinschätzung.
- **Hören und schreiben** (Diktat, Hören): `language-task` mit `languages: { source: de, target: fr }`; Item mit `audio` und `target`; für Zahlen
  `direction: to-source` mit `audio` und `source` (z. B. `75`). Der gesprochene Text ist eine richtige Antwort; Zahlen im gesprochenen Text ausschreiben.
- **Zuordnen und Auswählen**: Quizblöcke `single-choice`, `matching`, `true-false`; jede falsche Option mit `info`, die die Regel nennt.
- **Lücke und Formen**: `language-task` Modus `gap`, `choice` (mit `distractors` je Lücke), `table` (Formentabelle von être und avoir).
- **Übersetzen**: `language-task` `write`; die Aufgabe sagt „ohne Artikel“, wo nur das Wort gefragt ist; Varianten `(…|…)`; `form`: Akzent zählt, Großschreibung und Satzzeichen nur Hinweis (`case: hint`,
  `punctuation: hint`).
- **Zahlen erzeugen** (Seite 3): `generated`; Datei `src/data/zahlen.yaml` mit Feldern `n`, `fr`, `hinweis`, alle Zahlen von 0 bis 100; Aufgabe
  „Schreibe die Zahl: soixante-quinze“, Antwort `n`; Fehler: `n - 10` bei 70 bis 79 usw.
- **Rückmeldung**: 2 bis 3 `mistakes` je Aufgabe; jede Meldung nennt die Regel („Zu s’appeler gehört das m’: je m’appelle“), nie nur „falsch“. Typische Fehler:
  je appelle, je suis 11 ans, le école, il appelle, tu suis/je es, ou als „o-u“ gelesen.
- **Audio**: MP3 in `src/audio/`, gemacht mit Skill `lernapps-audio` (`scripts/lernapps_audio.py`), zwei Stimmen, vom Ersteller gewählt: Léa `ff_siwis` (weiblich), Malik `pierre` (männlich);
  Wörter, Zahlen und Sätze ohne Sprecher `ff_siwis`; freigegeben durch den Ersteller; Dateinamen kleingeschrieben, `.mp3`; der Text der Datei ist eine richtige Antwort der Aufgabe. Nach jeder Änderung des Satzes die Datei neu
  machen (`--force`).

## Figures

- Eigene SVG-Zeichnungen in `src/images/szene-<seite>.svg`, keine Fotos; `source: eigene Zeichnung`, `licence: CC-BY-4.0`.
- Figurenstil: Kopf und weicher, abgerundeter Torso, ohne Hals, Arme und Beine (Wunsch des Erstellers). Léa: kurze braune Haare, rote Jacke, hellere Haut; Malik:
  schwarze Locken, Brille, blauer Rucksack (ein Träger sichtbar). Skizze: `.vibe/sketches/figuren-lea-malik.svg`.
- Jede Zeichnung hat `alt` (nennt, wer links und rechts steht) und `caption` (nennt Figuren, Wort auf Schildern mit Bedeutung). Auf 360 px lesbar; ein Bild gibt nie die Lösung einer Übung vor.
- Gleiche Farben der Figuren auf allen Seiten; Hintergrund hell.

## Sources

- Lernlandkarte Französisch (Kompetenzen, Ids): `https://lernapps.net/apps/map/franzoesisch.json`.
- Grundwortschatz Französisch: `https://lernapps.net/apps/map/franzoesisch/grundwortschatz/` (geöffnet).
- Wikipedia „Französische Sprache“ (Aussprache) und „Französische Grammatik“, CC BY-SA 4.0, nur Fakten, keine Sätze; Aussprache einzelner Wörter prüft jemand mit
  Französisch-Kenntnissen vor der Veröffentlichung (nicht geprüft).
- KMK-Bildungsstandards Erste Fremdsprache (2023), nur zur Einordnung des Ziels. Keine Videos. Stimmen: siehe `src/audio` und die Medienübersicht (`medien/`).

## Adding a chapter or round

1. Kompetenzen wählen: die nächsten Lücken der Richtstufe 5-6 in `https://lernapps.net/apps/map/franzoesisch.json`, deren `requires` in der App geübt sind; drei bis acht je Kapitel.
2. Ordner `src/kapitel-<n>/` mit `chapter.yaml` (`title`, `summary`, `pages` mit allen Seiten) und je Seite `src/kapitel-<n>/<seite>.yaml` (`title`, `description`,
   `competencies`, `blocks`) nach „Content structure“; Kapitel in `src/app.yaml` unter `chapters` ergänzen.
3. Wörter nur aus Stufe A1 des Grundwortschatzes, jedes mit Bedeutung; eine Szene mit Léa und Malik je Seite in `src/images/szene-<seite>.svg`.
4. Übungen aus den Mustern oben; Ton: Sätze sammeln und mit Skill `lernapps-audio` erzeugen, anhören lassen.
5. `npx --no -- lernapps check`, Bilder prüfen (`npx --no -- lernapps screenshots --desktop`), Commit pro Seite; Plan anlegen (`increment-template.md`) und dieses Dokument anpassen.

## Rules learned from mistakes

None yet.
