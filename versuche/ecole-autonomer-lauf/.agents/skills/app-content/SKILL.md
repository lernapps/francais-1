---
name: app-content
description: Use for any content work in this app - researching, writing, extending, correcting or reviewing its competencies, chapters, pages, rounds, questions, exercises, figures, terms or sources. This app's own content decisions; they take precedence over the generic lernapps content skills. Load it before you change any content.
---

# Content guide of this app

## Curriculum

- Französisch als erste weitere Fremdsprache, 1. Lernjahr, Klasse 5 (Richtstufe 5-6 der Lernkarte). Kein Land und keine Schulform genannt.
- Orientierung: KMK-Bildungsstandards für die erste Fremdsprache; das Dokument wurde nicht gelesen, keine Einheit zitiert (not checked). Die Reihenfolge bestimmt die Lernkarte `https://lernapps.net/apps/map/franzoesisch.json` (`requires`).
- Kein Material der Creatorin; die Inhalte sind selbst geschrieben, die Creatorin prüft am Ende.
- Format 2, Einheits-App: `subject: franzoesisch` in `src/app.yaml`. Eine Seite übt Kompetenzen genau eines Strangs.

## Competencies

Ein Kapitel `ecole` ("À l'école – Mon premier jour"), Ordner `src/ecole/`, Seiten in dieser Reihenfolge (ids der Karte, Wortlaut der Karte):

1. `artikel-bestimmt.yaml`, `competencies: [bestimmter-artikel]`: Ich kann den bestimmten Artikel le, la, l' und les richtig vor ein Nomen setzen.
2. `zahlen.yaml`, `[zahlen-bis-100]`: Ich kann die Zahlen bis 100 verstehen und sagen, auch soixante-dix, quatre-vingts und quatre-vingt-dix.
3. `artikel-unbestimmt.yaml`, `[unbestimmter-artikel]`: Ich kann den unbestimmten Artikel un, une und des verwenden.
4. `uhrzeit.yaml`, `[uhrzeit]`: Ich kann nach der Uhrzeit fragen und sie angeben.
5. `datum.yaml`, `[datum-wochentage-monate]`: Ich kann Wochentage, Monate und ein Datum angeben, zum Beispiel mon anniversaire, c'est le 3 mai.
6. `schule.yaml`, `[schule-und-schulalltag]`: Ich kann über meine Schule, meinen Stundenplan und meine Schulsachen sprechen.
7. `alltagstexte.yaml`, `[alltagstexte]`: Ich kann Anzeigen, Plakate, Flyer und Schilder lesen und ihnen gezielt Angaben wie Datum, Uhrzeit und Preis entnehmen.

Jede `requires` einer Seite liegt auf einer früheren Seite; keine Recap-Seite, kein `ahead`. Exercise-ids: `<seite>-<muster>-<n>`, z. B. `artikel-bestimmt-waehlen-1`.

## Content structure

- Jede Seite hat Abschnitte mit festen ids in dieser Reihenfolge: `einstieg` (Ziel in Kinderworten und Szene von Léa und Noé), `woerter` (neue Wörter, jedes mit Artikel und Bedeutung, mit Hören und Nachsprechen), `merke` (Box "Merke", nennt den typischen Fehler), `uebung` (mindestens vier Übungen von leicht nach schwer), `postkarte` (Anwendung, Schritt der Postkarte), `weiter` (ein Satz, was als Nächstes kommt). Titel passen zum Inhalt der Seite.
- Eine neue Idee pro Seite. Höchstens 350 Wörter Lesetext und 4 Textblöcke hintereinander; innerhalb der ersten 4 Blöcke eine Figur, Tabelle oder Übung.
- Seite 7 (`alltagstexte.yaml`) hat statt `woerter` den Abschnitt `texte` (Stundenplan, Plakat) und endet statt mit `weiter` mit `rueckblick` (Rückblick auf das Kapitel und Nachsprechen zum Abschluss).
- Geschichte: Léa (10) und Noé (11), gezeichnet, neu an einer Schule in Lyon; sie schreiben eine Postkarte an ihre deutsche Partnerklasse. Ihre Namen, ihr Alter und die Schule bleiben auf jeder Seite gleich. Keine Figuren aus Büchern, Filmen oder Marken.
- Einzel-Auswahl (`single-choice`) braucht `links` und `info` auch an der richtigen Option. Jede Seite hat `scope` (und `src/app.yaml` hat `scope` mit `text` und `out`), weil Seite 6 eine `open-task` hat.

## Terminology

- Kinder werden mit "du" angesprochen, kurze Sätze, Dinge aus ihrem Schultag.
- Grammatikbegriffe auf Deutsch, einfach und kurz: "Artikel", "Verb", "Plural"; nicht mehr als nötig.
- Jedes französische Wort steht mit Artikel (le livre, la table, l'école, les sacs) und mit deutscher Bedeutung, bevor eine Übung danach fragt.
- Aussprache: kein Lautschriftzeichen; Hören und Nachsprechen statt Regeln.
- Vermieden: "falsch" ohne Grund; Fachwörter wie "Genus" oder "Determinativ".

## Exercise patterns

Jede Übung steht im Abschnitt `uebung`. Es gibt keine Datendatei: kein Block liest Wörter aus einer Datei, die Wörter stehen als Tabelle (`woerter`) und in den Items der Seite.

- **Wortkarte mit Artikel** (Benennen; Beispiel `artikel-bestimmt-beschriften-3` in `src/ecole/artikel-bestimmt.yaml`): `labelled-figure` (`legend: false`) im `material`, `language-task` mode `write`, Items mit `marker`. Variiert: das Wort.
- **Artikel wählen** (Form): `language-task` mode `choice` mit `distractors`; Fehlermeldung nennt das Geschlecht bzw. den Anfangslaut.
- **Lückensatz**: mode `gap`.
- **Hören und schreiben**: `language-task` mit `audio` (Diktat von Zahlen, Uhrzeiten, Daten).
- **Nachsprechen**: `speaking-task`, 1–10 Items mit `audio` und `text`; zählt als Übung der Seite, nicht in einer Selbsteinschätzung.
- **Zahlen ableiten** (Seite 2, `zahlen.yaml`): `language-task` mode `table` (60 + 10 = soixante-dix, 4 × 20 = quatre-vingts), danach `write` und `number` (soixante-quinze = 75, Fehler 65 und 15 mit Meldung).
- **Zuordnen** (`matching` mit `distractors`): Seiten 2, 3, 4, 5, 6, 7; links Deutsch oder Ziffern, rechts Französisch.
- **Einzelauswahl** (`single-choice`): Einstieg jeder Seite (Frage zum Satz oder Artikel) und Textverständnis auf Seite 7.
- **Wahr/falsch** (`true-false`): Seite 4 (heure/heures) und Seite 7 (Eintritt).
- **Uhrzeit** (Seite 4, `uhrzeit.yaml`): Uhr als Figur nur zur Erklärung (`images/uhren.svg`, Alt nennt die drei Zeiten); die Aufgaben geben die Uhrzeit als Text (`Es ist 9 Uhr.`) und verlangen `Il est neuf heures.` mit Varianten `(a|b)` nur, wo eine zweite Form richtig ist.
- **Wochentage ordnen** (Seite 5, `datum.yaml`): `ordering`; danach `write` des Datums mit `(12|douze)` und `(premier|1er)`.
- **Stundenplan und Plakat lesen** (Seite 7): `table` und `figure` (`images/poster.svg`) im Abschnitt `texte`, danach Fragen mit Rückmeldung.
- **Selbst vorstellen** (Seite 6, `schule.yaml`): `open-task` mit drei Punkten (je suis, j'ai + Artikel, j'ai + Fach); nur diese Seite hat eine `open-task`. Die Postkartensätze auf den anderen Seiten sind `language-task` mode `write`.
- Je Item 1–3 `mistakes` mit Regel in der Meldung: le/la (Geschlecht gehört zum Wort), l'/les, "je suis" (bin) und "j'ai" (habe), Zahlen ab 70, Uhrzeit mit "heure(s)", Plural-s nicht hörbar (Artikel zeigt den Plural). Jede richtige Variante gelistet, sonst zählt sie als falsch.
- Die Muster wechseln von Seite zu Seite; nicht dieselben drei Arten auf jeder Seite.

## Figures

- Gezeichnetes SVG in `src/images/` (Beispiel `klassenzimmer.svg`), mit `alt` (was gezeigt wird) und Beschriftung (worauf man schaut); nie die Lösung im Bild.
- Klassenzimmer mit nummerierten Markern (`klassenzimmer.svg`, Seite 1), Türschilder (`tueren.svg`, 2), Schultasche (`tasche.svg`, 3), Uhren (`uhren.svg`, 4), Kalenderblatt (`kalender.svg`, 5), Federtasche (`federtasche.svg`, 6), Plakat (`poster.svg`, 7); der Stundenplan ist eine Tabelle. Zeichnungen, keine Fotos; keine Stereotype. Léa und Noé gleich gezeichnet auf allen Seiten.
- Figuren funktionieren bei 360 px Breite und ohne Farbe als alleinigem Zeichen. Bildquelle und Lizenz: selbst erstellt, CC BY 4.0.
- Keine Komponente (`prefer-built-in-block`): alles mit Blöcken lösbar.

## Sources

- Lernkarte Französisch (Kompetenzen und Reihenfolge), Auszug von der Creatorin über die Karte übermittelt.
- Grundwortschatz A1 (FLELex / Beacco, CC BY-NC-SA 4.0): nur einzelne Wörter, mit Quelle genannt (Creatorin: einverstanden); keine Listenstruktur übernommen.
- Wörter außerhalb der Liste nur, wenn die Situation sie braucht; sie werden auf der Seite erklärt und hier gelistet: (bisher keine).
- Zweitquellen je Kompetenz: nicht geöffnet (not checked). Kein Material der Creatorin im Repository.
- Audio: KI-Stimmen (Französisch), gemacht mit Skill `lernapps-audio`, als KI-erzeugt markiert, in `src/audio/`; die Medienübersicht listet sie.

## Adding a chapter or round

1. Kompetenz-id aus der Lernkarte wählen; ihre `requires` müssen auf früheren Seiten stehen (sonst Recap-Seite oder `ahead`).
2. Ordner `src/<kapitel>/` mit `chapter.yaml` (title, summary, Reihenfolge `pages`); neue Kapitel in `src/app.yaml` unter `chapters` eintragen, vollständige Listen.
3. Seite `src/<kapitel>/<seite>.yaml` mit `title`, `description`, `competencies: [<id>]`, `scope`, Abschnitten `einstieg`, `woerter`, `merke`, `uebung`, `postkarte`, `weiter`.
4. Wörter als Tabelle im Abschnitt `woerter` der Seite (mit Artikel, Bedeutung).
5. Übungen aus den Mustern oben; Audio nach Skill `lernapps-audio`; Fehlermeldungen je Item.
6. `npx --no -- lernapps check`; Content-Guide ändern, wenn sich ein Muster ändert; ein Commit je Seite.

## Rules learned from mistakes

None yet.
