---
# Read by the hooks, the review, the evals. Schema: @lernapps/tooling/guidance/plan-front-matter.v1.schema.json
# Keep all four keys.
# Archetype, null until chosen in Explore. Allowed values: explainer, interactive, quiz.
archetype: explainer
# Current phase. Allowed values: explore, plan, code, commit. Change the value line below, never this comment.
phase: commit
# prePushFailures: written by the pre-push hook. Never change it.
prePushFailures: 0
# failedChecks: failed rules and runs, written by lernapps check and the hooks. Never change it.
failedChecks: { checks-pass: 2 }
---

# Plan: <app name>, first version

<!--
For you, the assistant.
1. Path: `.vibe/plans/01-<short name>.md`. Every later change gets its own plan from the increment template.
2. Read this plan before each step. One phase at a time, tasks in order.
3. Task done → tick `[x]` at once and move it to "Completed" of its phase. An unticked box counts as not done.
4. New task found → add it.
5. Each phase names its skills. Load a skill when its task comes, not before. Read it in full, from its file.
6. Checkpoint: stop, ask, wait for the creator's answer. A message sent before the question is no yes.
   Only a checkpoint waits. A phase's last box → set the next phase and go on in the same message.
7. At most 2 questions per message, one topic each. No questions inside drafts or lists.
8. Work on the branch `work`, locally: push nothing before Commit. Commit puts the app on GitHub and brings `work`
   into `main`.
9. Plan in the creator's language. Keep headings and front matter keys. Delete a comment once its part is filled.
10. Begin each reply to the creator with the phase in `phase:`, and at a checkpoint the word checkpoint:
    "**Plan · Checkpoint**", "**Code**". The creator always knows where you are.
-->

*Started <date>. Explore, Plan, Code, Commit.*

## Goal

<!-- 1–2 sentences: what learners do, what they learn. -->

## Key decisions

- Archetyp `explainer`: Kinder brauchen Erklärung (Artikel, Zahlen, Uhrzeit) vor dem Üben, mit Übungen dazwischen; Hören und Sprechen (KI-Stimme, `speaking-task`) gibt es nur hier. Nicht `quiz` (keine Erklärseiten), nicht `interactive` (kein Spiel/Timer gewünscht). Kann nicht: Aussprache nicht bewerten (Kind bewertet sich selbst), keine eigenen Farben, kein Timer, kein Spiel.
- Format 2, `subject: franzoesisch`, `languages: [de]` (guess). `scope` in `src/app.yaml` und auf jeder Seite: nötig wegen `open-task` (Postkarte) (guess, Entscheidung der Plan-Phase; Code bestätigt nach `references/structure.md`).
- Keine Selbsteinschätzung (`selfAssessment`) in der ersten Version (guess): Der Skill `lernapps-explainer-self-assessment` lag im Test nicht vor; Sprechaufgaben sind darin ohnehin nicht möglich, die Seiten haben viele Schreibaufgaben. Kann in einem Inkrement folgen.
- Sprechaufgaben (`speaking-task`) zählen als Übung der Seite, können aber nicht in eine Selbsteinschätzung; Selbsteinschätzung entscheidet Commit.

## Notes

**Strang/Fach:** Einheitsapp (unit app) `subject: franzoesisch` (Karte sagt `explainerFocus: competency`, laut Parent-Auszug nicht selbst geprüft); eine Seite = ein Strang. Archetyp `explainer`, Format 2.

**Curriculum-Orientierung:** Kein Land genannt → KMK-Bildungsstandards. Nicht geprüft (not checked): Das Dokument habe ich nicht gelesen; keine Einheit zitiert. Die Reihenfolge entscheidet die Lernkarte (`requires`).

**Kompetenzen (ids und Wortlaut der Karte, Klassenband 5-6), ein Kapitel "À l'école", Seiten in dieser Reihenfolge:**
1. `bestimmter-artikel` (grammatik, Schritt 1): Ich kann den bestimmten Artikel le, la, l' und les richtig vor ein Nomen setzen.
2. `zahlen-bis-100` (wortschatz, Schritt 1): Ich kann die Zahlen bis 100 verstehen und sagen, auch soixante-dix, quatre-vingts und quatre-vingt-dix.
3. `unbestimmter-artikel` (grammatik, Schritt 2): Ich kann den unbestimmten Artikel un, une und des verwenden.
4. `uhrzeit` (wortschatz, Schritt 2): Ich kann nach der Uhrzeit fragen und sie angeben.
5. `datum-wochentage-monate` (wortschatz, Schritt 2): Ich kann Wochentage, Monate und ein Datum angeben, zum Beispiel mon anniversaire, c'est le 3 mai.
6. `schule-und-schulalltag` (wortschatz, Schritt 3): Ich kann über meine Schule, meinen Stundenplan und meine Schulsachen sprechen.
7. `alltagstexte` (texte, Schritt 3): Ich kann Anzeigen, Plakate, Flyer und Schilder lesen und ihnen gezielt Angaben wie Datum, Uhrzeit und Preis entnehmen.

Voraussetzungen (`requires`) liegen alle früher in der Reihenfolge: unbestimmter-artikel ← bestimmter-artikel; uhrzeit, datum ← zahlen-bis-100; schule ← unbestimmter-artikel, uhrzeit, datum; alltagstexte ← uhrzeit, datum. Keine Recap-Seite, kein `ahead` nötig. Alle sieben: laut Creatorin von keiner App geübt (`practisedBy` leer).

**Wie Kinder dorthin kommen / Fehlerbilder (eine Zeile je Kompetenz):**
- bestimmter-artikel: Wörter mit Bild/Szene zuordnen, Geschlecht als Teil des Wortes lernen (immer mit Artikel); Meldung bei le/la-Verwechslung nennt das Geschlecht des Worts, bei l'/les den Anfangslaut bzw. Plural.
- zahlen-bis-100: Zahlenbausteine ableiten (soixante + dix = 70, quatre-vingts = 4×20), dann Hör-Diktat; Fehlerbild: Zahlen ab 70.
- unbestimmter-artikel: un/une/des an Dingen in der Schultasche; Gegenüberstellung le/un; Meldung bei Plural-s ("hört man nicht, des/les zeigt den Plural").
- uhrzeit: Uhr-Bilder ablesen, "il est … heures" bilden, hören und eintragen; Fehlerbild: Zahl + heures vergessen, il est/est-ce.
- datum-wochentage-monate: Kalenderblatt lesen, Datum bilden (c'est le 3 mai), Wochentage ordnen.
- schule-und-schulalltag: Schulsachen und Fächer (mit Artikel) benennen, Stundenplan sprechen; Hören und Nachsprechen; "j'ai" vs. "je suis" (j'ai un stylo / je suis Léa) mit eigener Meldung.
- alltagstexte: Stundenplan und Schild lesen, Angaben (Fach, Uhrzeit, Tag) entnehmen; Verständnisfragen.

**Didaktik:** Jede Seite: Situation → Einführung (jedes Wort mit Bedeutung und Artikel) → Üben von leicht nach schwer (Auswahl → Lücken → Schreiben → Übersetzen) → Anwenden (Postkarte). Hören/Nachsprechen mit KI-Stimme (Französisch ist erlaubt, Skill `lernapps-audio`). Grammatikwörter deutsch, kurz.

**Umfang (scope):** In: die sieben Seiten, Grundwortschatz A1 rund um Schule, Zahlen, Uhrzeit, Datum; Hören und Sprechen. Out: Verben konjugieren (nur feste Wendungen wie j'ai, je suis, il est, c'est), Aussprache-Strang (keine eigene Seite; Aussprache nur über Hören/Nachsprechen), Zahlen über 100, freies Schreiben ohne Prüfung. Datenbereich: Zahlen 0–100 vollständig, Wochentage und Monate alle, Schulfächer und Schulsachen aus dem A1-Wortschatz (école, classe, cantine, cour, sac, stylo, trousse, livre, cahier*, …). *Wörter ausserhalb der A1-Liste nur falls nötig und dann erklärt und in "Content method" gelistet. Sprachen: Seiten Deutsch; Beispiele Französisch (guess: nur `de`).

**Quellen:** (1) Lernkarte Französisch, Auszug über @parent erhalten, Kompetenzen wörtlich; (2) Grundwortschatz A1 (FLELex/Beacco, CC BY-NC-SA 4.0), Liste über @parent; die Lizenz NC/SA verträgt sich nicht mit CC BY 4.0 für Inhalte, deshalb keine Listenstruktur kopieren, nur einzelne Wörter verwenden (guess; zu klären im Checkpoint). (3) Zweitquellen je Kompetenz (z. B. Wikipedia/Serlo): nicht geöffnet, not checked. Kein Material der Creatorin.

**Screenshot-Kontrolle (Code):** Alle 7 Figuren je in eigenem Bild bei 360 px und 1280 px angesehen (Klassenzimmer, Türschilder, Tasche, Uhren, Kalender, Federtasche, Plakat); Seitenbild von Seite 1 bei 360 px angesehen, kein Querscrollen; Lerner-Check von Seite 1 durch Sub-Agent im Browser. Seiten 2–7 nicht einzeln von einem Sub-Agent als Lerner geprüft (nur `lernapps check` und Figuren).

**Durchgang der ganzen App als Kind der Klasse 5 (Sub-Agent, 360 und 1280 px) und was daraufhin geändert wurde:**
Gefunden: (1) Kalender-Figur zeigte samedi, der Text lundi, und das Datum sprang (3. Mai, Montag, 3. Oktober); (2) Seiten 3, 4, 5 nannten die falsche "letzte Seite"; (3) Seite 3: Text mit Federtasche, Bild mit Buch; (4) nach j'ai steht das Fach ohne Artikel, Seite 7 verlangt ihn; (5) Titel "0 à 100", aber 0 und 21 bis 69 fehlen, 77 und 25 werden gefragt; (6) "salut" und "le français" nirgends eingeführt, "et", "voici", "à" unerklärt; (7) die Orte der Geschichte springen; (8) Stundenplan passt nicht zur Postkarte (Montag 8 Uhr: Mathe und Sport).
Geändert: Figuren Kalender (lundi) und Tasche (Federtasche statt Buch); Datum auf Seite 5 durchgehend Montag, 3. Mai; Verweise "auf Seite 1" und "auf Seite 2"; Geschichte in einem Schultag (Flur, Pause, Klassenzimmer); Zahlen 0, 21 bis 69, et, Übung `zahlen-zehner-7`; Merke und Fehlermeldungen zu j'ai ohne Artikel; Wörter salut, et, voici, à, le français, midi/minuit eingeführt; Postkartensatz Seite 7 passt zum Stundenplan; Überschrift "Klein schreiben, Grundzahl sagen"; Scope Seite 6 ohne "Datum".
Nicht geändert: "Deine Fassung kann trotzdem richtig sein" bei anderen richtigen Formen (Runtime); Zimmer 80 steht auf keiner Tür; die Schnitte von Ort und Zeit auf Seite 7 (Plakat samedi 14 juin).

**Offen:** Lizenzfrage A1-Liste (Creatorin: einzelne Wörter mit Quelle okay); ob "Mon premier jour"-Geschichte genügt; Prüfung durch die Creatorin am Ende.

## Explore

<!--
- Find out what the app teaches, for whom, how much and how it looks. All content questions belong here; Plan only
  maps the answers onto the archetype.
- Ask. Write no code, run no `create`.
- An answer counts only in the creator's words under "Answers". Never tick a topic you assumed.
- Skills: `lernapps-app`, `lernapps-exercise-patterns`, `lernapps-<archetype>-design`, `lernapps-content-research`.
-->

### Tasks

- [x] The skills of the phases are in `.agents/skills/` (`npx --yes @lernapps/tooling init <short name>` put them there
      and wrote this plan; the app commits them). `.agents/skills/lernapps-app` missing → stop and tell the creator
      the folder was not started with `init`. `git branch --show-current` prints `work`; else `git switch -c work`.
- [x] Load skill `lernapps-app`. Tell the creator in two sentences what a lernapps app is and where it will live: at
      their own address, free, public, and once listed as a copy on lernapps.net. The technical part (GitHub) comes at the end, and you do it.
- [x] Interview: ask the topics "Goal" and "Learners" of "Answers".
- [x] No fixed content yet ("an app for my class", "a gap on the map") → load skill `lernapps-map-assignment` and
      write its assignment first; its yes answers the topics it covers.
- [x] Load skill `lernapps-exercise-patterns` and read the patterns of the subject: how will learners practise what
      the goal names? The kind of practice points to the archetype, as the skill says.
- [x] Choose the archetype as skill `lernapps-app` says, from the kind of practice: read the README of each
      archetype in question, tell the creator what the chosen one can and cannot do. Write it and its reason under
      "Key decisions". Set `archetype`.
- [x] Install the archetype's skills (Testmodus: nicht installiert; `lernapps-explainer-design` und README über @parent erhalten und gelesen): `npx --no -- lernapps skills --archetype <archetype>`. Load skill
      `lernapps-<archetype>-design`.
- [x] Interview: ask the other topics of "Answers" in order. Skip a topic an earlier answer covers; note which.
      A confirmed assignment covers Goal, Learners, Content, Amount and Languages; an explainer has no "Look and
      feel" (its look is the runtime's): note "covered by the assignment" or "fixed by the archetype", ask only the
      rest. No answer → ask once more; still none → write your assumption with "(guess)". Done when every topic has
      an answer, a note or a guess.
- [x] Load skill `lernapps-content-research`. Research as it says. Under "Notes": curriculum orientation (none
      when the content comes from the map, an assignment or a strand: the map gives the order), competencies by
      chapter as "Ich kann …", verified sources. No competencies → not done. First the learning map as
      skill `lernapps-content-research` says: recommend a strand that fits (`<subject>/<strand>`), else `none`; with a
      strand, only its competencies, by their ids from the map. A map with `explainerFocus: competency` also allows a
      unit app across strands (`subject: <subject>`), one strand per page. Write both under "Notes", and how they map onto
      chapters and pages (an explainer: as a rule one page per competency; competencies that build on each other, by
      the map's `requires`, share a chapter, in that order).
- [x] Under "Notes", one line per competency: how learners get there (derive, not only read off; e.g. a tree diagram
      shows how a probability comes about), which misconception the feedback catches.
- [x] Under "Notes", the scope: what is in, what is out and why, the data range (e.g. "all main-group elements",
      never a silent "1–20"), the languages.
- [x] Fetch https://lernapps.net/apps/schemas/entry.v1.schema.json and read each property's description. Ask what
      helps teachers and parents find the app. Fill "Entry draft". Search words: one or two words each, as people
      type them.
- [x] **Checkpoint:** research (Creatorin: "Ja, die Recherche passt so"; Wörter einzeln aus A1-Liste mit Quellenangabe okay). Show in plain words: the strand or why none, curriculum orientation (not with a
      strand), competencies by chapter (with their ids) and their pages, didactic approach, scope, every "(guess)", sources and how you
      checked them, what is unchecked, archetype and reason. With a strand, the map decides the structure: competencies
      that build on each other (its `requires`) share a chapter, in that order; no curriculum search is needed for it.
      Stop and wait. Changes → change, ask again.
- [x] Set `phase: plan`: change the value line (`grep '^phase:'` prints `phase: plan`).

### Answers

<!-- The interview: per topic the creator's answer, in their words. Keep the topics. -->

- Goal: Kinder der 5. Klasse lernen "à l'école": Schulsachen, Fächer, Zahlen, Uhrzeit, Datum, Stundenplan. Auftrag "À l'école – Mon premier jour" (7 Seiten, Postkarte an die Partnerklasse) von der Creatorin bestätigt ("Ja, der Auftrag stimmt so").
- Learners: Französisch, 1. Lernjahr, Klasse 5 (Band 5-6), praktisch ohne Vorkenntnisse (einige kennen Bonjour). Kein Land/Schulform genannt → KMK-Bildungsstandards.
- Model and focus: Beispiel-App `examples/franzoesisch` des Explainers; Schwerpunkt Übungen mit Hören und Nachsprechen (guess: Katalog-Modell nicht gelesen, da lernapps.net nicht abgerufen werden darf).
- Hurdles: le/la verwechseln (Geschlecht der Wörter überhaupt), Plural-s mitsprechen, "je suis" und "j'ai" durcheinanderbringen, Zahlen ab 70, Uhrzeit ("il est … heures"), Wörter schreiben, wie sie gehört werden (Creatorin).
- Content: Ich schreibe die Inhalte selbst aus dem Grundwortschatz A1; kein eigenes Material; die Creatorin schaut am Ende drüber.
- Amount: erste Version = sieben Seiten in einem Kapitel laut bestätigtem Auftrag (covered by the assignment).
- Languages: Seiten deutsch, Beispiele französisch (laut Auftrag). Hören und Sprechen mit KI-Stimme: ja, die Creatorin wünscht es ("das Nachsprechen lieben die Kinder").
- Look and feel: fixed by the archetype (ruhig wie ein Arbeitsblatt, Dark Mode folgt dem Gerät).
- Terms: Grammatikbegriffe auf Deutsch, einfach und kurz ("Artikel", "Verb"), nicht mehr als nötig (Creatorin).

### Entry draft

<!-- YAML valid against the entry schema, with its property names. Only known values, never invented. -->

```yaml
title: À l'école – Mon premier jour
subject: franzoesisch
grades: [5]
summary: >-
  Léa und Noé sind neu an einer Schule in Lyon und schreiben eine Postkarte an ihre Partnerklasse.
  Dabei lernst du die Artikel, Zahlen, Uhrzeit und Wochentage und sprichst über Schule und Stundenplan.
  Du hörst, sprichst nach und übst mit Rückmeldung.
keywords: [Französisch, Schule, Klasse 5, Anfänger, Stundenplan, Uhrzeit, Zahlen, Artikel, Nachsprechen, Vokabeln Schule, Französisch Klasse 5]
fitness:
  account: false
  install: false
  storage: device
  thirdParty: none
# creator (Creatorin: "Frau Beispiel", ohne eigene Webseite) wird im Entry eingetragen: creator: { name: Frau Beispiel }
# Offen, nicht erfunden, kommen in Commit: url, source, commit, checked.
# topics (Tiefenlinks) folgen, wenn die Seiten feststehen.
```

### Completed

## Plan

<!--
- Map the confirmed content onto the archetype: structure, screens or pages, exercise patterns, data files,
  components.
- No new content questions. A content gap → back to Explore; say so.
- Confirmable in one read. After the yes, work on your own: at most 3 creator turns until the listing.
- Skills: `lernapps-<archetype>-design` and `lernapps-exercise-patterns`, both loaded in Explore.
-->

### Tasks

- [x] `grep '^phase:'` prints `phase: plan`; else set it.
- [x] Map the content as skill `lernapps-<archetype>-design` says; reread it if it is no longer in view.
- [x] Choose a pattern per competency as skill `lernapps-exercise-patterns` says (loaded in Explore; reread it if it
      is no longer in view). Write "Content method".
- [x] Write the Code tasks under "Code": pages or screens, their content, what each shows. Each ends in a commit:
      one task, one commit. Steps too small for a commit of their own → one task.
      The first task: one complete page or screen as the pattern for the others (`early-preview`).
- [x] Each screen, component or interactive exercise: a sketch (static SVG or image, or the steps with what
      learners see after each). Words alone are not enough. Keep sketch files in `.vibe/sketches/`, which `create` leaves alone.
- [x] Show the creator, short: goal, competencies by chapter (chapters along the map's `requires`), entry draft, tasks, sketches; the content method in
      plain words (what learners see and do, what it cannot do). At most 2 questions.
- [x] **Checkpoint:** confirm the plan and the content method, with the sketches shown. Stop and wait for an
      explicit yes. Changes → change, ask again. No `create` before the yes.
- [x] Set `phase: code`: change the value line (`grep '^phase:'` prints `phase: code`).

### Content method

**Quelle der Wörter:** Grundwortschatz A1 (FLELex/Beacco, CC BY-NC-SA 4.0), nur einzelne Wörter, mit Quellenangabe; jedes Wort mit Artikel und Bedeutung eingeführt, bevor eine Übung danach fragt. Wörter außerhalb der Liste (z. B. cahier, gomme, règle): nur wenn die Situation sie braucht, erklärt, hier gelistet (wird in Code ergänzt).

**Listening/speaking:** ja, Französisch hat KI-Stimmen (Skill `lernapps-audio`); `speaking-task` zum Nachsprechen (Skizze `.vibe/sketches/sprechen-nachsprechen.svg`) und `audio` in `language-task` für Hör-Diktat; Erlaubnis und Stimmen vorher nach Skill `lernapps-audio` klären.

**Übungsmuster (Name · Kompetenz · Form):**
- *Wortkarte mit Artikel* · Benennen · `labelled-figure` mit Markern + `language-task` mode `write` (Wort mit Artikel). Daten: `src/data/schulwoerter.yaml` (je Wort: fr, de, Geschlecht, Audio).
- *Artikel wählen* · Form wählen · mode `choice` mit `distractors` (le/la, l'/les).
- *Lückensatz* · Wort im Satz · mode `gap`.
- *Hören und schreiben* · Hörverstehen/Schreibung · `language-task` mit `audio` (Zahlen, Uhrzeit, Datum).
- *Nachsprechen* · Sprechen · `speaking-task`.
- *Zahlenbausteine ableiten* · Zahlen ab 70 · `table` (soixante + dix) dann `write`.
- *Uhr lesen* · Uhrzeit · `table`/Uhrbild als gezeichnete Figur, danach `write` ("Il est … heures").
- *Kalender lesen / ordnen* · Datum · `ordering` (Wochentage) + `write`.
- *Stundenplan lesen* · Alltagstext · `table` als `material` + Fragetypen (Auswahl, Zuordnung).
- *Postkarte* · Anwenden · `open-task` mit Formpunkten (nur auf Seite 6/7; sonst Lückensatz).

**Figuren (Lernhandlung):** Klassenzimmer-Zeichnung mit Markern: Ganzes = das Zimmer, Zahl = Dingnummer, Kinder tragen zum Marker das Wort mit Artikel ein; zeigt nur das Gegebene, nie die Lösung. Uhr (gezeichnet): Zeiger = Stunde/Minute, Kinder lesen ab. Kalenderblatt, Stundenplan als Tabelle: Zeilen = Tage, Spalten = Stunden; Kinder entnehmen Fach und Zeit. Keine Komponente (`prefer-built-in-block`): alles mit Blöcken lösbar.

**Mistakes je Muster:** le/la: "Das Wort ist weiblich, deshalb la"; l'/les: Anfangsvokal bzw. Plural wird gehört (les/des); "je suis" vs "j'ai": suis = bin, ai = habe, "j'ai 10 ans"; Zahlen 70–99 (soixante-dix = 60+10; quatre-vingts = 4×20); Uhrzeit: Zahl + heure(s); Hörschreibung: Plural-s nicht hörbar, Artikel zeigt Plural.

**Engagement je Seite (Opening · Change · Reward · Story):**
1 Artikel: erst Zimmer beschriften, dann Regel · hören/lesen/schreiben · Zimmer ist beschriftet · Léa und Noé beschriften ihr Klassenzimmer.
2 Zahlen: Zimmernummern hören und eintragen · hören/rechnen/sprechen · du kannst bis 100 · Nummern auf Postkarte.
3 un/une/des: Schultasche auspacken · Wahl/Lücke/Schreiben · du packst die Tasche richtig · Léa packt für den ersten Tag.
4 Uhrzeit: Pausenglocke, "Wie spät ist es?" · ablesen/hören/sagen · du sagst die Zeit · Stundenbeginn.
5 Datum: Kalender der Klasse, Geburtstage · ordnen/schreiben · du nennst Datum · Postkartendatum.
6 Schule: Schulsachen und Fächer benennen · Zuordnung/Schreiben/Nachsprechen · du erzählst von deiner Schule · Postkarte nimmt Gestalt an.
7 Texte: Stundenplan und Schild lesen · Fragen/Zuordnung · du liest echte Angaben · Postkarte fertig, Rückblick auf das Kapitel.

**Voraussetzungen:** alle `requires` stehen auf früheren Seiten; keine Recap-Seite, kein `ahead`.

**Wie ein späterer Agent ein Kapitel ergänzt:** neue Seite = Datei `src/<kapitel>/<seite>.yaml` mit Kompetenz-id der Karte, Wörter in `src/data/schulwoerter.yaml`, Audio mit Skill `lernapps-audio`, Reihenfolge nach `requires`; steht im Content-Guide.

### Completed

## Code

<!--
- Build the app from the archetype and the confirmed plan, locally on `work`. Work on your own.
- Commit after each task, literally: one task, one commit, its box ticked in it; the hooks check. Never one commit
  for several tasks: join them into one task in the plan first. A check fails → skill `lernapps-cli`. Fix from the message; never
  bypass a hook.
- Undecidable → choose, mark "(guess)" under "Key decisions", go on.
- Creator asks for a change → first say your reading in one sentence ("Ich nehme alle 44 Hauptgruppenelemente
  auf."); never narrow it silently. Content change → update "Notes" too.
- Skills: `lernapps-cli`, `lernapps-<archetype>`, `lernapps-content-questions`, and the app's content guide
  `app-content`.
-->

### Tasks

- [x] `grep '^phase:'` prints `phase: code`; else set it.
- [x] Load skill `lernapps-cli`. Create the app in this plan's folder as it says. `create` keeps this plan. Never
      write the app by hand.
- [x] Fill the content guide `.agents/skills/app-content/SKILL.md` from "Notes" and "Content method"
      (`app-content-guide`). Keep its nine headings and fill each: Curriculum, Competencies, Content structure,
      Terminology, Exercise patterns, Figures, Sources, Adding a chapter or round, Rules learned from mistakes
      ("None yet." until the first). `grep -c "FILL IN" .agents/skills/app-content/SKILL.md` prints 0. Commit it
      before any content.
- [x] Load skill `lernapps-<archetype>` and the content guide. Questions with options and feedback: also skill
      `lernapps-content-questions`.
- [x] An explainer: decide on `scope` as `references/structure.md` of skill `lernapps-explainer` says. Needed with an
      `open-task` or the creator's material: then `scope` in `src/app.yaml` and on every page
      (`explainer-scope-matches`). Write the choice under "Key decisions".
- [x] Seite 1 `bestimmter-artikel` komplett (ohne Hör-/Sprechaufgaben, kommen mit dem Audio-Task; `lernapps check` grün) (Muster für alle anderen; Szene, Wortkarten, Merke, Übungen, Postkarte; Hör-/Sprechaufgabe zunächst ohne Audio-Datei wenn Erlaubnis fehlt): commit auf `work`.
- [x] **Checkpoint:** the pattern page (Creatorin: "Ja, die Seite gefällt mir") (`early-preview`): check it against the design rules, let a sub-agent check
      it as a learner, show it to the creator, wait for the answer. A change → change the pattern first.
- [x] Daten: entfällt (kein Block liest Wörter aus einer Datei; Wörter stehen als Tabelle auf der Seite; Content-Guide angepasst).
- [x] Seite 2 `zahlen-bis-100`; commit.
- [x] Seite 3 `unbestimmter-artikel`; commit.
- [x] Seite 4 `uhrzeit`; commit.
- [x] Seite 5 `datum-wochentage-monate`; commit.
- [x] Seite 6 `schule-und-schulalltag`; commit.
- [x] Seite 7 `alltagstexte` mit Kapitel-Rückblick; commit.
- [x] Audio mit Skill `lernapps-audio` (38 MP3; ff_siwis, pierre; Creatorin hört am Ende an, Freigabe = Commit) (erst Erlaubnis und Stimmen klären), MP3s in `src/audio/`, Medienübersicht prüfen; commit.
- [x] The content guide matches what was built (`app-content-matches`).
- [x] `npx --no -- lernapps check` passes.
- [x] Look at a screenshot of every screen and state (start, each mode, pause, end), desktop and 360 px. Compare
      each with the confirmed sketches; each figure in its own image (`npx --no -- lernapps screenshots --desktop`).
      Your tools cannot show an image: check each screen in the browser instead (text, element boxes at both widths),
      write that under "Notes" and tick the box.
- [x] Every box of Explore, Plan and Code ticked.
- [x] Set `phase: commit`: change the value line (`grep '^phase:'` prints `phase: commit`).
      No checkpoint here: set it before you ask or report anything, then start Commit in the same message.
      The creator asked to stop before publishing (e.g. a trial) → stop instead: leave this box open, the reason
      under it.

### Completed

## Commit

<!--
- Put the app on GitHub, publish it with the creator's yes, then list it. A push to `main` publishes.
- Open the pull requests (to `main`, to the catalog) without asking: they publish nothing; their preview and result
  are what the creator decides on.
- Skills: `lernapps-explainer-self-assessment` (an explainer), `lernapps-github`, `lernapps-commit`,
  `lernapps-listing`.
-->

### Tasks

- [x] `grep '^phase:'` prints `phase: commit`; else set it.
- [x] An explainer: load skill `lernapps-explainer-self-assessment` (nicht geladen; Entscheidung "keine Selbsteinschätzung" mit Grund unter Key decisions) (missing → `npx --no -- lernapps skills --archetype
      explainer`). Add the self-assessment as it says, or
      write under "Key decisions" why the app has none. Commit; the hooks check.
- [ ] Load skill `lernapps-github`. Repo and Pages as it says: ask the repo name and every click only the creator can
      make in one message.
- [ ] Push `work`, open the preview pull request, see its checks to green as the skill says.
- [ ] **Checkpoint:** publish. Show what the app does and the preview link from the comment "Vorschau der App"; ask
      whether it may go online; put any open click into the same question. Wait for the yes.
- [ ] Load skill `lernapps-commit`. Publish as skill `lernapps-github` says: `work` into `main` as one squash commit
      with the message from this plan, the run of `Pages` watched to the end.
- [ ] Open the address the job `deploy` printed; confirm the app shows. Use that address, never a derived one.
- [ ] Load skill `lernapps-listing`. Complete the entry draft (e.g. the address).
- [ ] Fill the retrospective.
- [ ] Commit this plan on `main` and push it: the listing check and the review read it there.
- [ ] **Checkpoint:** list. Open the listing pull request as the skill says, without asking first: the pull request
      is the review. See it to "bestanden", then show the creator the pull request and its result; change nothing in
      it without their word.
- [ ] Plan changed since its last push → commit it on `main`, push again.

### Completed

## Retrospective

<!-- At the end of Commit, before the listing pull request. Facts, short, no names. Read by review and evals. -->

### Phases reached

Explore, Plan, Code durchlaufen (Checkpoints research, plan, Musterseite von der Creatorin bestätigt); Commit nur teilweise: Testmodus ohne GitHub, alles lokal auf `work` committet, `lernapps check` grün; nicht veröffentlicht.

### Creator turns after the plan

Zwei Rückfragen im Code: Audio (Download ja, Stimmen ff_siwis und pierre) und die Musterseite (Ja, Seiten 2–7 nach dem Muster). Beides Antworten über @parent.

### Where I had to guess

- Nur Deutsch als Seitensprache (`languages: [de]`).
- Suchwörter im Entry-Entwurf (die Creatorin ergänzte zwei).
- Katalog-Modell nicht gelesen (kein Abruf von lernapps.net im Test); Link-Ziele zur Lernkarte (`/c/<id>/`) nicht geöffnet.
- Zweitquellen und KMK-Dokument nicht geöffnet.
- Keine Selbsteinschätzung in der ersten Version.
- Seiten 2–7 nicht einzeln von einem Sub-Agent als Lerner geprüft; Audio nicht angehört (die Creatorin hört am Ende an, Freigabe = Commit).
- Hinweis aus dem Lerner-Check, nicht behebbar im Inhalt: Beschriftung "Teil 1 der Abbildung", Meldung "Deine Fassung kann trotzdem richtig sein" und das Feld "Lösung" in der Sprechaufgabe kommen aus der Runtime.
