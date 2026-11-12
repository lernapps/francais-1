---
# Read by the hooks, the review, the evals. Schema: @lernapps/tooling/guidance/plan-front-matter.v1.schema.json
# Keep all four keys.
# Archetype, null until chosen in Explore. Allowed values: explainer, interactive, quiz.
archetype: explainer
# Current phase. Allowed values: explore, plan, code, commit. Change the value line below, never this comment.
phase: explore
# prePushFailures: written by the pre-push hook. Never change it.
prePushFailures: 0
# failedChecks: failed rules and runs, written by lernapps check and the hooks. Never change it.
failedChecks: {}
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

## Notes

- Einheit: `subject: franzoesisch`, Stränge `aussprache`, `wortschatz`, `grammatik` (eine Strangart pro Seite).
- Richtstufe 5-6. Die Karte bestimmt die Reihenfolge, kein Lehrplan.
- Kapitel 1 „Bonjour, Léa und Malik!“ in dieser Reihenfolge: `laut-und-schrift`, `begruessen-und-vorstellen`, `zahlen-bis-100`, `subjektpronomen`, `verb-etre`, `bestimmter-artikel`, `verb-avoir`.
- Feste Wendungen ohne Grammatik: ma mère, un frère, c'est.
- Kein Ton-Prüfen: Nachsprechen bewerten die Kinder selbst, die App hört nicht zu.
- Wörter: aus dem Grundwortschatz Französisch (https://lernapps.net/apps/map/franzoesisch/grundwortschatz/, 1930 Wörter, Stufe A1 zuerst), geprüft beim Schreiben der Seiten. Ein Wort außerhalb der Liste nur, wenn die Szene es braucht; es wird dort erklärt. Die Beispielwörter im Auftrag sind noch nicht geprüft.

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
- [ ] Interview: ask the topics "Goal" and "Learners" of "Answers".
- [x] No fixed content yet ("an app for my class", "a gap on the map") → load skill `lernapps-map-assignment` and
      write its assignment first; its yes answers the topics it covers.
- [x] Load skill `lernapps-exercise-patterns` and read the patterns of the subject: how will learners practise what
      the goal names? The kind of practice points to the archetype, as the skill says.
- [x] Choose the archetype as skill `lernapps-app` says, from the kind of practice: read the README of each
      archetype in question, tell the creator what the chosen one can and cannot do. Write it and its reason under
      "Key decisions". Set `archetype`.
- [x] Install the archetype's skills: `npx --no -- lernapps skills --archetype <archetype>`. Load skill
      `lernapps-<archetype>-design`.
- [ ] Interview: ask the other topics of "Answers" in order. Skip a topic an earlier answer covers; note which.
      A confirmed assignment covers Goal, Learners, Content, Amount and Languages; an explainer has no "Look and
      feel" (its look is the runtime's): note "covered by the assignment" or "fixed by the archetype", ask only the
      rest. No answer → ask once more; still none → write your assumption with "(guess)". Done when every topic has
      an answer, a note or a guess.
- [ ] Load skill `lernapps-content-research`. Research as it says. Under "Notes": curriculum orientation (none
      when the content comes from the map, an assignment or a strand: the map gives the order), competencies by
      chapter as "Ich kann …", verified sources. No competencies → not done. First the learning map as
      skill `lernapps-content-research` says: recommend a strand that fits (`<subject>/<strand>`), else `none`; with a
      strand, only its competencies, by their ids from the map. A map with `explainerFocus: competency` also allows a
      unit app across strands (`subject: <subject>`), one strand per page. Write both under "Notes", and how they map onto
      chapters and pages (an explainer: as a rule one page per competency; competencies that build on each other, by
      the map's `requires`, share a chapter, in that order).
- [ ] Under "Notes", one line per competency: how learners get there (derive, not only read off; e.g. a tree diagram
      shows how a probability comes about), which misconception the feedback catches.
- [ ] Under "Notes", the scope: what is in, what is out and why, the data range (e.g. "all main-group elements",
      never a silent "1–20"), the languages.
- [ ] Fetch https://lernapps.net/apps/schemas/entry.v1.schema.json and read each property's description. Ask what
      helps teachers and parents find the app. Fill "Entry draft". Search words: one or two words each, as people
      type them.
- [ ] **Checkpoint:** research. Show in plain words: the strand or why none, curriculum orientation (not with a
      strand), competencies by chapter (with their ids) and their pages, didactic approach, scope, every "(guess)", sources and how you
      checked them, what is unchecked, archetype and reason. With a strand, the map decides the structure: competencies
      that build on each other (its `requires`) share a chapter, in that order; no curriculum search is needed for it.
      Stop and wait. Changes → change, ask again.
- [ ] Set `phase: plan`: change the value line (`grep '^phase:'` prints `phase: plan`).

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
summary: Léa und Malik begleiten Kinder durch einen Schultag auf Französisch. Sie hören, sprechen nach und üben Aussprache, Begrüßen, Zahlen, être, Artikel und avoir.
keywords: [Französisch, Anfänger, Aussprache, Zahlen, être, avoir]
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

- [ ] `grep '^phase:'` prints `phase: plan`; else set it.
- [ ] Map the content as skill `lernapps-<archetype>-design` says; reread it if it is no longer in view.
- [ ] Choose a pattern per competency as skill `lernapps-exercise-patterns` says (loaded in Explore; reread it if it
      is no longer in view). Write "Content method".
- [ ] Write the Code tasks under "Code": pages or screens, their content, what each shows. Each ends in a commit:
      one task, one commit. Steps too small for a commit of their own → one task.
      The first task: one complete page or screen as the pattern for the others (`early-preview`).
- [ ] Each screen, component or interactive exercise: a sketch (static SVG or image, or the steps with what
      learners see after each). Words alone are not enough. Keep sketch files in `.vibe/sketches/`, which `create` leaves alone.
- [ ] Show the creator, short: goal, competencies by chapter (chapters along the map's `requires`), entry draft, tasks, sketches; the content method in
      plain words (what learners see and do, what it cannot do). At most 2 questions.
- [ ] **Checkpoint:** confirm the plan and the content method, with the sketches shown. Stop and wait for an
      explicit yes. Changes → change, ask again. No `create` before the yes.
- [ ] Set `phase: code`: change the value line (`grep '^phase:'` prints `phase: code`).

### Content method

<!-- One line each: exercise patterns and where; figures and how they are made; data files; each component, what it
checks and cannot; how a later agent adds a chapter. Each figure, model and component: its learning action in two to
four sentences: the whole, what its parts and marks mean, what learners do and what stays the same, how that leads to
the statement (an explainer: rule `explainer-representation-explained`). A control without a part in it goes. An explainer on the map: per page its prerequisites (`requires`)
the app does not practise, and which get a recap page, which a link. Becomes the content guide in Code. -->

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

- [ ] `grep '^phase:'` prints `phase: code`; else set it.
- [ ] Load skill `lernapps-cli`. Create the app in this plan's folder as it says. `create` keeps this plan. Never
      write the app by hand.
- [ ] Fill the content guide `.agents/skills/app-content/SKILL.md` from "Notes" and "Content method"
      (`app-content-guide`). Keep its nine headings and fill each: Curriculum, Competencies, Content structure,
      Terminology, Exercise patterns, Figures, Sources, Adding a chapter or round, Rules learned from mistakes
      ("None yet." until the first). `grep -c "FILL IN" .agents/skills/app-content/SKILL.md` prints 0. Commit it
      before any content.
- [ ] Load skill `lernapps-<archetype>` and the content guide. Questions with options and feedback: also skill
      `lernapps-content-questions`.
- [ ] An explainer: decide on `scope` as `references/structure.md` of skill `lernapps-explainer` says. Needed with an
      `open-task` or the creator's material: then `scope` in `src/app.yaml` and on every page
      (`explainer-scope-matches`). Write the choice under "Key decisions".
- [ ] <the first task written in Plan, the pattern page; commit on `work`>
- [ ] **Checkpoint:** the pattern page (`early-preview`): check it against the design rules, let a sub-agent check
      it as a learner, show it to the creator, wait for the answer. A change → change the pattern first.
- [ ] <the other tasks written in Plan, after the pattern; after each, commit on `work`>
- [ ] The content guide matches what was built (`app-content-matches`).
- [ ] `npx --no -- lernapps check` passes.
- [ ] Look at a screenshot of every screen and state (start, each mode, pause, end), desktop and 360 px. Compare
      each with the confirmed sketches; each figure in its own image (`npx --no -- lernapps screenshots --desktop`).
      Your tools cannot show an image: check each screen in the browser instead (text, element boxes at both widths),
      write that under "Notes" and tick the box.
- [ ] Every box of Explore, Plan and Code ticked.
- [ ] Set `phase: commit`: change the value line (`grep '^phase:'` prints `phase: commit`).
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

- [ ] `grep '^phase:'` prints `phase: commit`; else set it.
- [ ] An explainer: load skill `lernapps-explainer-self-assessment` (missing → `npx --no -- lernapps skills --archetype
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

<!-- Last phase completed, checkpoints passed. E.g. "commit; confirmed, published". -->

### Creator turns after the plan

<!-- Number of creator messages after the confirmation, topic of each. Target: at most 3. -->

### Where I had to guess

<!-- Each gap in plan, skills, messages or answers, and your choice. "None" if none. -->
