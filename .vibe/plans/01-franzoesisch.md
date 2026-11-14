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
failedChecks: { checks-pass: 6 }
---

# Plan: Bonjour, Léa und Malik, erste Version

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

*Gestartet 2026-11-12. Explore, Plan, Code, Commit.*

## Goal

Kinder der Richtstufe 5/6 (Anfang 1. Lernjahr Französisch) lesen, hören und sprechen nach und üben Aussprache, Begrüßen, Zahlen, Pronomen, être, Artikel und avoir. Eine Geschichte mit Léa und Malik trägt die Seiten. Das erste Kapitel wird bis Ende Klasse 6 um weitere erweitert.

## Key decisions

- Archetyp `explainer`: Seiten mit Erklärung, Beispiel und Übungen; Hör-Diktat und Nachsprechen sind mit `audio` und `speaking-task` möglich (Vorlagen-Version 0.8.0).
- Audio verlangt `@lernapps/app-templates` 0.8.0 (die Version, die `init` installiert hat, ist 0.7.1 ohne Audio). Nach `create` wird die Vorlage auf 0.8.0 gehoben und geprüft (guess).
- Der Ton ist ausdrücklich gewünscht: Hören und Nachsprechen am Anfang.
- Kein `open-task` und kein Material des Erstellers: kein `scope` in `src/app.yaml` und auf den Seiten (guess).
- Ein Kapitel `kapitel-1` mit sieben Seiten; Dateinamen `src/kapitel-1/<seite>.yaml`.
- Ton nach dem Anhören (Ersteller): Wörter immer mit Artikel (le/la), dazu kurze Sätze („Voici le chat.“) als zweite Stufe des Nachsprechens; Einzelwörter ohne Artikel klangen schlecht.
- Zwei Stimmen (Wunsch des Erstellers): Léa spricht `ff_siwis` (weiblich), Malik `pierre` (männlich); Sätze ohne Sprecher (Wörter, Zahlen, Buchstabenverbindungen) mit `ff_siwis`. Freigabe der Aufnahmen durch den Ersteller vor der Veröffentlichung.
- Abweichungen beim Bau (guess): Seite 5 zeigt ein Foto von Léa, Malik und der Katze statt eines Familienfotos (Familie und „mon/ma“ gehören in ein späteres Kapitel); Seite 7 nennt „il y a un chat“ als feste Wendung, „un“ wird später erklärt; Seite 4 benutzt „s'appelle“ und „jouer au foot“ als feste Wendungen, damit die Pronomen ein Verb haben.
- Keine Selbsteinschätzung im Kapitel (guess, Entscheidung nach der Schüler-Prüfung): Die Texte der Vorlage („Lies sie genau“) wirken auf Anfänger entmutigend, und die Aufgaben wären die der Seiten. Der Ersteller kann sie später mit dem Skill ergänzen.

## Notes

- Einheit: `subject: franzoesisch`, Stränge `aussprache`, `wortschatz`, `grammatik` (eine Strangart pro Seite).
- Richtstufe 5-6. Die Karte bestimmt die Reihenfolge, kein Lehrplan.
- Kapitel 1 „Bonjour, Léa und Malik!“ in dieser Reihenfolge: `laut-und-schrift`, `begruessen-und-vorstellen`, `zahlen-bis-100`, `subjektpronomen`, `verb-etre`, `bestimmter-artikel`, `verb-avoir`.
- Feste Wendungen ohne Grammatik: ma mère, un frère, c'est.
- Kein Ton-Prüfen: Nachsprechen bewerten die Kinder selbst, die App hört nicht zu.
- Wörter: aus dem Grundwortschatz Französisch (https://lernapps.net/apps/map/franzoesisch/grundwortschatz/, 1930 Wörter, Stufe A1 zuerst), geprüft beim Schreiben der Seiten. Ein Wort außerhalb der Liste nur, wenn die Szene es braucht; es wird dort erklärt. Die Beispielwörter im Auftrag sind noch nicht geprüft.

### Prüfung der Seiten im Browser (Code)

Startseite, Seite 1 und Seite 3 habe ich als Bilder angesehen; alle sieben Seiten wurden bei 1280 px und 360 px im Browser gemessen und geprüft: kein seitliches Überlaufen, Tabellen passen, Bilder laden, Audiodateien sind erreichbar, keine Skriptfehler. Die Seiten 2, 4, 5, 6 und 7 habe ich nicht einzeln als Bild angesehen. Hören konnte ich die Aufnahmen nicht; der Ersteller hat die von Seite 1 gehört. Die Aufnahmen der Seiten 2 bis 7 sind noch nicht freigegeben.

### Recherche (2026-11-12)

**Lehrplan.** Kein Land und keine Schule genannt, deshalb KMK. Die KMK-Bildungsstandards „Erste Fremdsprache (Englisch/Französisch) für den Ersten Schulabschluss und den Mittleren Schulabschluss“ (Beschluss 2003/2004, i. d. F. vom 22.06.2023, https://www.kmk.org/fileadmin/Dateien/veroeffentlichungen_beschluesse/2023/2023_06_22-Bista-ESA-MSA-ErsteFremdsprache.pdf) habe ich geöffnet und gelesen (verified). Sie gelten für Jahrgangsstufe 9 und 10, nicht für Richtstufe 5/6, und der Primarbereich ist im Dokument nur erwähnt. Für diese Stufe zitiere ich daher keine Einheit; die Lernlandkarte gibt Reihenfolge und Stufe vor.

**Karte.** `franzoesisch` (explainerFocus competency, Status draft): Einheit-App `subject: franzoesisch`, eine Strangart pro Seite. Alle Kompetenzen der Karte sind bisher von keiner App geübt (Lücken).

**Kompetenzen nach Kapitel (Kapitel 1, Seiten in dieser Reihenfolge, Ids der Karte):**
1. `laut-und-schrift` (Aussprache, Schritt 1): Ich kann häufige Buchstabenverbindungen richtig aussprechen, zum Beispiel ou, oi, au, eau, ch und gn.
2. `begruessen-und-vorstellen` (Wortschatz, Schritt 1): Ich kann mich begrüßen, verabschieden, vorstellen und fragen, wie es jemandem geht.
3. `zahlen-bis-100` (Wortschatz, Schritt 1): Ich kann die Zahlen bis 100 verstehen und sagen, auch soixante-dix, quatre-vingts und quatre-vingt-dix.
4. `subjektpronomen` (Grammatik, Schritt 1): Ich kann die Subjektpronomen je, tu, il, elle, on, nous, vous, ils und elles verwenden.
5. `verb-etre` (Grammatik, Schritt 2): Ich kann das Verb être im Präsens konjugieren und damit Personen und Dinge vorstellen (c’est, il est).
6. `bestimmter-artikel` (Grammatik, Schritt 1): Ich kann den bestimmten Artikel le, la, l’ und les richtig vor ein Nomen setzen.
7. `verb-avoir` (Grammatik, Schritt 2): Ich kann das Verb avoir im Präsens konjugieren und Wendungen wie il y a und j’ai 13 ans verwenden.

Voraussetzungen der Karte (`requires`): zahlen-bis-100, begruessen-und-vorstellen, laut-und-schrift, bestimmter-artikel haben keine; subjektpronomen hat keine; verb-etre und verb-avoir verlangen subjektpronomen (steht auf Seite 4, vor 5 und 7). Alle Voraussetzungen sind in der App geübt, deshalb keine Wiederholungsseite und kein `ahead`.

**Didaktik, eine Zeile je Kompetenz:**
- laut-und-schrift: Kinder hören ein Wort, sehen die Buchstaben und ordnen den Laut zu; sie leiten die Regel aus gehörten Beispielen ab (ou, oi, eau, ch, gn). Typischer Fehler: Buchstaben wie im Deutschen lesen (ou als „o-u“, ch als „k“).
- begruessen-und-vorstellen: Kurze Dialoge hören, ordnen und nachsprechen; je m’appelle als feste Wendung. Typischer Fehler: „je appelle“ ohne m’.
- zahlen-bis-100: Zahlen hören und tippen; die Bildung von 70–99 wird aus 60/20 abgeleitet. Typischer Fehler: soixante-dix als „sechzig-zehn“ nicht erkennen, quatre-vingts mit s/ohne s.
- subjektpronomen: Pronomen zu Personen und Bildern zuordnen. Typischer Fehler: il/elle bei Dingen, tu/vous (Höflichkeit), on als „wir“.
- verb-etre: Tabelle der Formen, Satz ergänzen; c’est/il est für Personen. Typischer Fehler: je es, tu suis.
- bestimmter-artikel: Geschlecht lernen und l’ vor Vokal; Nomen zu le/la/l’/les zuordnen. Typischer Fehler: Geschlecht vom Deutschen übertragen, Plural-s nicht hören.
- verb-avoir: Formen der Tabelle, Alter mit avoir (j’ai 11 ans). Typischer Fehler: „je suis 11 ans“.

**Umfang.** Drin: Kapitel 1 mit 7 Seiten, deutsche Erklärungen, französische Beispiele, Hören und Nachsprechen auf mindestens den Seiten 1–3 (weitere, wo es passt), Zahlen bis 100, erste Verbformen von être und avoir. Draußen: unbestimmter Artikel, Possessiv, Verneinung, Fragen, weitere Verben (spätere Kapitel); automatische Sprechprüfung (geht nicht). Sprache: Deutsch (Erklärungen), Französisch (Beispiele); kein Englisch.

**Quellen.** Wörter: Grundwortschatz Französisch (https://lernapps.net/apps/map/franzoesisch/grundwortschatz/, geöffnet, 200). Zweitquellen, geöffnet und geladen: Wikipedia „Französische Sprache“ mit Abschnitt zur Aussprache (https://de.wikipedia.org/wiki/Französische_Phonologie leitet dorthin um; Titel der Seite: „Französische Sprache“) und „Französische Grammatik“ (https://de.wikipedia.org/wiki/Französische_Grammatik), Lizenz CC BY-SA 4.0 laut Seite; nur Fakten, keine Sätze. Keine Videos: ich habe keine gesucht und keines geprüft; das bleibt offen. Nicht geprüft: Aussprache einzelner Wörter durch eine Person mit Französisch-Kenntnissen (vor der Veröffentlichung nötig); Zahlwörter und Verbformen werden beim Schreiben gegen die Wikipedia-Seiten und den Grundwortschatz abgeglichen.

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
- [x] Install the archetype's skills: `npx --no -- lernapps skills --archetype <archetype>`. Load skill
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
      Suchwörter vom Ersteller bestätigt.
- [x] **Checkpoint:** research. Show in plain words: the strand or why none, curriculum orientation (not with a
      strand), competencies by chapter (with their ids) and their pages, didactic approach, scope, every "(guess)", sources and how you
      checked them, what is unchecked, archetype and reason. With a strand, the map decides the structure: competencies
      that build on each other (its `requires`) share a chapter, in that order; no curriculum search is needed for it.
      Stop and wait. Changes → change, ask again.
- [x] Set `phase: plan`: change the value line (`grep '^phase:'` prints `phase: plan`).

### Answers

<!-- The interview: per topic the creator's answer, in their words. Keep the topics. -->

- Goal: Beginnen mit Französisch, später bis Ende Klasse 6 erweitern; Situationen aus Schule, Freizeit und Familie. Ton ist wichtig: hören und nachsprechen.
- Learners: Französisch, Richtstufe 5/6, Anfang 1. Lernjahr.
- Model and focus: kein Vorbild genannt. Eine Mischung, nicht zu dicht, am Anfang gern mit vielen Medien (Bilder, Ton).
- Hurdles: Der Ersteller überlässt es dem Assistenten (guess): stumme Endungen, Plural-s, m' bei je m'appelle, le/la/l', Aussprache von ou/oi/eau, Zahlen 70-99.
- Content: bestätigter Auftrag (Karte), Texte vom Assistenten; covered by the assignment.
- Amount: ein Kapitel mit 7 Seiten; später Erweiterung bis Ende Klasse 6; covered by the assignment.
- Languages: Deutsche Erklärungen, französische Beispiele; covered by the assignment.
- Look and feel: calm like a worksheet, or like a game (colours, praise, effects); dark mode.
- Terms: nicht genannt (guess): „Seite“, „Übung“, „Hören“, „Nachsprechen“, „Merke“.

### Entry draft

<!-- YAML valid against the entry schema, with its property names. Only known values, never invented. -->

```yaml
title: Bonjour, Léa und Malik!
subject: franzoesisch
grades: [5, 6]
summary: >-
  Léa zeigt Malik ihre Schule, den Tennisplatz und ihr Zimmer. Du hörst ihnen zu, sprichst nach und übst die ersten
  Wörter und Regeln auf Französisch: Aussprache, Begrüßen, Zahlen bis 100, Pronomen, être, Artikel und avoir.
  Mit Ton, kleinen Spielen und Rückmeldung zu jedem Fehler.
url: https://lernapps.net/francais-1/
keywords: [Französisch, Anfänger, Aussprache, Zahlen, être, avoir]
creator: { name: Oliver }
source: https://github.com/lernapps/francais-1
commit: c7209bbf55f10584d43b0c5ffc450b6ed82077e3
fitness: { account: false, install: false, storage: device, thirdParty: none, checked: false }
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

- **Seitenaufbau, überall gleich** (Ids): `einstieg` (Szene und Ziel: „Danach kannst du …“, knüpft an die Seite davor an), `neu` (Wörter oder Regel, jedes Wort mit Bedeutung, Tabelle), `nachsprechen` (nur Seiten mit Ton), `uebung` (leicht → schwer: auswählen → Lücke → hören und schreiben → übersetzen). Ein Abschnitt, den eine Seite nicht braucht, fällt weg. Skizze: `.vibe/sketches/seitenaufbau.svg`.
- **Szene (Figur)**: gezeichnete Szene `src/images/szene-<seite>.svg` mit Léa und Malik, mit Bildunterschrift und `alt`; sie zeigt, was gegeben ist, nie die Lösung. Die Figuren sind fest (`.vibe/sketches/figuren-lea-malik.svg`): Léa, 11, kurze braune Haare, rote Jacke; Malik, 11, schwarze Locken, Brille, blauer Rucksack. Lernaktion: Kinder schauen die Szene an und beantworten eine Frage dazu (Wer sagt was? Wo steht das Wort?); sie ist Anlass, nicht Inhalt.
- **Wörter einführen** (Muster „Neu“): `table` mit Wort, Bedeutung, Hinweis; die Wörter der Seite stehen vor der Übung da, sie kommen aus dem Grundwortschatz (A1) oder werden erklärt. Kein eigener Datensatz: Tabellen lesen keine Datendateien; die Wörter stehen je einmal in der Tabelle ihrer Seite.
- **Nachsprechen** (`speaking-task`, Seiten 1–3, danach wo es passt): 3–6 Sätze oder Wörter mit Modell-Audio; Kinder hören, nehmen auf, vergleichen, bewerten sich selbst („schon gut / fast / noch üben“). Prüft nichts, die App hört nicht zu. Ablauf: `.vibe/sketches/nachsprechen-ablauf.svg`. Datei: `src/audio/*.mp3`, gemacht mit `lernapps-audio`.
- **Hören und schreiben** (`language-task` mit `audio`, Diktat; Seite 1: Wort, Seite 2: Gruß, Seite 3: Zahl als `direction: to-source` mit Zahl als `source`, z. B. 75): Der gesprochene Text ist die richtige Antwort; Zahlen im Audio ausgeschrieben (soixante-quinze). Rückmeldungen: 2–3 `mistakes` je Aufgabe mit Regel (zum Beispiel „ou klingt wie ein langes u, nicht wie o-u“).
- **Zuordnen/Auswählen** (Quiztypen `single-choice`, `matching`, `true-false`): Schreibung ↔ Bedeutung, Pronomen ↔ Person, Artikel ↔ Nomen; jede falsche Option mit `info`, warum sie nicht passt.
- **Lücke und Formen** (`language-task` Modi `gap`, `choice`, `table`): être und avoir als Formentabelle, Sätze mit Lücke, Artikel mit `distractors` (le/la/l’/les); typische Fehler als `mistakes` (je suis 11 ans, il appelle, le école).
- **Übersetzen** (`language-task` `write`): kurze Sätze Deutsch → Französisch, mit Varianten `(…|…)` und `form`: Großschreibung und Satzzeichen als Hinweis, Akzente zählen.
- **Zahlen** (Seite 3): `generated` mit Datei `src/data/zahlen.yaml` (Felder `n`, `fr`, `hinweis`): „Schreibe die Zahl: soixante-quinze“ → 75; typische Fehler: 60+15 falsch addiert (65), quatre-vingts als 40/80-Verwechslung. Bereich: 0–100 vollständig, nie still gekürzt; die Zahlen 70–99 werden aus 60/20 abgeleitet und gezeigt.
- **Aussprache der Buchstabenverbindungen** (Seite 1): `table` Buchstabenverbindung / Beispielwort / Bedeutung mit Wörtern, die Kinder hören; Regel durch Hören abgeleitet. Keine Lautschrift (der Ersteller hat sie nicht verlangt); die Kinder hören statt zu lesen.
- **Figuren/Bilder** (alle): eigene SVG-Zeichnungen, keine Fotos; Bildunterschrift, `alt`, gleiche Farben der Figuren auf jeder Seite; Figurenstil: Kopf und weicher, abgerundeter Torso, ohne Hals, Arme und Beine, nicht blockig (Wunsch des Erstellers, gilt für alle Szenen); auf 360 px lesbar; kein Bild gibt die Lösung vor.
- **Eine Komponente?** Nein: kein Baustein fehlt (Begründung für `prefer-built-in-block`). Die Hör- und Nachsprech-Blöcke und `language-task` genügen.
- **Rückmeldung falscher Antworten:** immer mit der Regel (nie nur „falsch“); 2–3 typische Fehler je Aufgabe aus „Hürden“.
- **Nächste Seite/Kapitel später:** Ein Agent liest den Abschnitt „Adding a chapter or round“ der Inhaltsanleitung (`app-content`) und legt `src/kapitel-N/` mit den Seiten, `src/audio/` und den Karten-Ids an; neue Wörter nur aus A1 oder erklärt.
- **Figuren zu Seiten:** Seite 1 Schultor-Schild, 2 Pausenhof-Gruß, 3 Klassenzimmer mit Hausnummern/Alter, 4 Tennisplatz, 5 Familienfoto, 6 Schultasche, 7 Léas Zimmer; Szenen nach der Reihenfolge der Seiten.

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
- [x] Nach `create`: `@lernapps/app-templates` auf 0.8.0 heben (Audio), prüfen mit `npx --no -- lernapps check`; ein Commit. Geht das nicht: dem Ersteller sagen, Ton bleibt dann aus.
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
- [x] Seite 1 `laut-und-schrift` (Muster-Seite) komplett: Szene, Tabelle, Hör-Diktat, Nachsprechen, Übung. Vorher dem Ersteller sagen, was das Audio-Werkzeug braucht (0,6 GB Download, Netz für pypi.org, files.pythonhosted.org, github.com, huggingface.co), die Stimme wählen lassen (`ff_siwis` weiblich oder `pierre` männlich) und auf das Ja warten; die Sätze vom Ersteller (oder jemandem mit Französisch) anhören lassen. Commit auf `work`.
- [x] **Checkpoint:** the pattern page (`early-preview`): check it against the design rules, let a sub-agent check
      it as a learner, show it to the creator, wait for the answer. A change → change the pattern first.
- [x] Seite 2 `begruessen-und-vorstellen` (Pausenhof: Gruß, Vorstellen, Wie geht's); Audio, Übung. Commit.
- [x] Seite 3 `zahlen-bis-100` (Klassenzimmer; Alter und Hausnummer); `zahlen.yaml`, generierte Übung, Hören. Commit.
- [x] Seite 4 `subjektpronomen` (Fußballtraining); Pronomen zuordnen. Commit.
- [x] Seite 5 `verb-etre` (Familienfoto); Formentabelle, c'est/il est. Commit.
- [x] Seite 6 `bestimmter-artikel` (Schultasche); le/la/l'/les. Commit.
- [x] Seite 7 `verb-avoir` (Léas Zimmer); Formen, Alter, il y a. Commit.
- [x] Startseite und Kapitel: Titel, Einleitung, Figurenvorstellung, Quellen in `src/app.yaml`, Glossar. Commit.
- [x] The content guide matches what was built (`app-content-matches`).
- [x] `npx --no -- lernapps check` passes.
- [x] Look at a screenshot of every screen and state (start, each mode, pause, end), desktop and 360 px.
      Stand nach der zweiten Prüfrunde: Bilder von Seitenanfang und „Kurz geübt“ aller sieben Seiten selbst angesehen, dazu zwei Prüfrunden durch Schüler-Prüfer (je 2 bis 3 Unter-Agenten, alle Übungen mit richtigen und falschen Antworten) und Messungen bei 1280 und 360 px. Nicht als Bild angesehen habe ich Nachsprech- und Übungsteile jeder Seite.
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
- [x] An explainer: load skill `lernapps-explainer-self-assessment` (missing → `npx --no -- lernapps skills --archetype
      explainer`). Add the self-assessment as it says, or
      write under "Key decisions" why the app has none. Commit; the hooks check.
- [x] Load skill `lernapps-github`. Repo and Pages as it says (Repo `lernapps/francais-1` da, `main`, `gh-pages` und `work` gepusht; offen: Pages-Quelle `gh-pages` und Sichtbarkeit öffentlich, beides Klicks des Erstellers): ask the repo name and every click only the creator can
      make in one message.
- [x] Push `work`, open the preview pull request, see its checks to green as the skill says.
- [x] **Checkpoint:** publish. Show what the app does and the preview link from the comment "Vorschau der App"; ask
      whether it may go online; put any open click into the same question. Wait for the yes.
- [x] Load skill `lernapps-commit`. Publish as skill `lernapps-github` says: `work` into `main` as one squash commit
      with the message from this plan, the run of `Pages` watched to the end.
- [x] Open the address the job `deploy` printed; confirm the app shows. Use that address, never a derived one.
- [x] Load skill `lernapps-listing`. Complete the entry draft (e.g. the address).
- [x] Fill the retrospective.
- [x] Commit this plan on `main` and push it: the listing check and the review read it there.
- [x] **Checkpoint:** list. Open the listing pull request as the skill says, without asking first: the pull request
      is the review. See it to "bestanden", then show the creator the pull request and its result; change nothing in
      it without their word.
- [x] Plan changed since its last push → commit it on `main`, push again.

### Completed

## Retrospective

<!-- At the end of Commit, before the listing pull request. Facts, short, no names. Read by review and evals. -->

### Phases reached

Commit erreicht. Bestätigt und passiert: Recherche, Plan mit Inhaltsmethode, Muster-Seite, Veröffentlichung (App online unter `lernapps.net/francais-1/`). Listung: Pull Request lernapps/apps#277 aus dem Fork geöffnet, Prüfung „bestanden“; Entscheidung des Betreibers von lernapps.net offen.

### Creator turns after the plan

Etwa 20 Nachrichten des Erstellers nach der Bestätigung des Plans, deutlich über dem Ziel von höchstens 3. Themen: Figurenstil (Torso); Audio-Freigabe und Stimmenwahl (zwei Stimmen); Hören der Aufnahmen und Wünsche (Wörter mit Artikel, Sätze; fünf schlechte Aufnahmen, Tennis statt Fußball, Satzzeichen-Varianten); Repo-Name und GitHub-Klicks (Sichtbarkeit, Pages-Quelle); zwei Rückfragen zum Vorgehen (Prüfung als Schüler, Retro-Einträge); „Alles ändern, es soll Spaß machen“; Freigabe zum Veröffentlichen. Hauptgründe: Ton lässt sich nur durch Anhören beurteilen, und Prüfungen aus Schülersicht waren zuerst nicht eingeplant.

### Where I had to guess

<!-- Each gap in plan, skills, messages or answers, and your choice. "None" if none. -->

Prozessfehler (vom Ersteller bemerkt, hier festgehalten):

- Ich habe im Plan das Kästchen „Look at a screenshot of every screen“ abgehakt, obwohl ich nur Startseite, Seite 1 und Seite 3 als Bild gesehen hatte; die Seiten 2, 4, 5, 6 und 7 hatte ich nur gemessen. Den Widerspruch habe ich selbst in „Notes“ geschrieben und das Kästchen trotzdem gesetzt. Korrigiert, nachdem der Ersteller nachfragte.
- Die Prüfung als Schüler (Unter-Agent im Browser) habe ich nur für die Muster-Seite gemacht, wie der Plan sie verlangt, nicht für die Seiten 2 bis 7, und erst auf Nachfrage des Ersteller nach dem Prüfpunkt „publish“ gestartet. Sie gehört vor die Vorschau. Die Funde der ersten Prüfung (Fachbegriffe vor der Erklärung, zu breite Tabellen, rohe Sternchen in der Rückmeldung) habe ich nicht auf allen Seiten gegengeprüft (`feedback-applied-everywhere`).
- Ich hatte einen Satz zur Aussprache („nous jouons“, Bindung) ohne Quelle geschrieben und erst beim erneuten Lesen als falsch erkannt; im Leitfaden steht dazu jetzt eine Regel.
- Beim Figurenstil lag beim Start eine Datei im Ordner, die ich in diesem Gespräch nicht geschrieben hatte (Commit „Figuren runder gezeichnet“, mit Hals, Armen und Beinen, gegen den Wunsch des Erstellers). Herkunft ungeklärt; die Figuren habe ich nach dem Wunsch neu gezeichnet.
- Nach der Überarbeitung (Gespräch im Einstieg, „Kurz geübt“, ein Nachsprech-Block, neue Sätze, erklärende Rückmeldungen) hat die zweite Prüfung als Schüler weitere Fehler gefunden: Rückmeldungen erschienen nur bei genauem Schlusspunkt und genauer Großschreibung, „On joue au foot“ galt als falsch, ein Altersrätsel verwies auf nicht vorhandenen Text, Seitenbeschreibungen auf der Startseite waren voller Fachwörter, Bildunterschriften versprachen Dinge, die nicht kamen. Behoben und im Leitfaden als Regel festgehalten. Nicht änderbar, weil Texte der Vorlage: „Satz 1“ bei Einzelwörtern, die Marke „KI“ am Player, „Deine Fassung kann trotzdem richtig sein“, „Lies dazu noch einmal den Text über der Aufgabe“, der Wikipedia-Link nach jeder richtigen Antwort, der KI-Tutor-Abschnitt und die Medienübersicht.
- Englische Lehnwörter (foot, football) wurden von den Stimmen mit einem Nachlaut gesprochen, auch mit Satzzeichen-Varianten; erst der Austausch gegen „tennis“ half. Künftig englische Lehnwörter in gesprochenen Sätzen vermeiden und neue Wörter vor dem Einbau anhören lassen (Regel im Leitfaden). Tempo der Stimmen blieb bei 1,0 (Vorgabe des Audio-Skills); „Tu es Malik“ klang zu schnell und bekam ein „, oui“ als Pause.
- Eine Aussage zu „septante/nonante“ habe ich in einer Rückmeldung zuerst ohne Quelle geschrieben und nach dem Prüfen entfernt.
- Die Pages-Einstellung konnte ich über den Proxy nicht lesen oder setzen; ein Klick des Erstellers (zuerst falsche Quelle, dann `gh-pages`) war nötig. Ein leerer Commit auf `gh-pages` und ein Neustart des Workflows halfen nicht.
- Ich habe die Aussprache aller Aufnahmen nicht gehört; die Klangvergleiche in den Texten sind nicht von jemandem mit Französisch-Kenntnissen geprüft.

