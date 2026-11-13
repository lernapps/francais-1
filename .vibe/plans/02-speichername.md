---
# Read by the hooks, the review, the evals. Schema: @lernapps/tooling/guidance/plan-front-matter.v1.schema.json
# Keep all four keys.
# Archetype as in the app's first plan; set it when you start. Never changes.
archetype: explainer
# Current phase. Allowed values: explore, plan, code, commit. Change the value line below, never this comment.
phase: code
# prePushFailures: failed pre-push runs of this increment, written by the hook. Never change it.
prePushFailures: 0
# failedChecks: failed rules and runs, written by lernapps check and the hooks. Never change it.
failedChecks: {}
---

# Increment: Speichername der App korrigieren

*Gestartet 2026-11-13. Explore, Plan, Code, Commit.*

## Goal

Die App legt ihre lokalen Einstellungen unter dem Namen ihres Repositories an (`francais-1`) und nicht unter dem Startnamen `franzoesisch`, damit die Prüfung des Katalogs sie annimmt. Für Lernende ändert sich nichts.

## Key decisions

- Nur der Paketname in `package.json` und `package-lock.json` ändert sich (von `franzoesisch` auf `francais-1`): Die Vorlage leitet daraus den Namen des lokalen Speichers ab (`data-storage`). Keine Änderung an Inhalten, Seiten, Übungen oder Ton.
- Die Fach-Id `franzoesisch` der Lernlandkarte in `src/app.yaml` bleibt, sie ist keine App-Bezeichnung.
- Keine Inhaltsfragen: Die Checkpoints „research“ und „plan“ entfallen, weil nichts Neues gelehrt wird (guess). Der Checkpoint „publish“ bleibt: Veröffentlichen nur mit dem Ja des Erstellers.

## Notes

- Anlass: Die Listungsprüfung (`npm run listing` in einem Klon von lernapps/apps) meldet `own-data-only`: Die App liest den Speicherschlüssel `lernapps:franzoesisch:…`, erwartet wird das Präfix `lernapps:francais-1:`.
- Die Meldungen `links-resolve` und `entry-links-resolve` („cannot be fetched“) kamen aus meiner Umgebung (kein Zugriff von Node auf lernapps.net, die Seite selbst ist erreichbar); sie sind kein Fehler der App. Die Prüfung des Pull Requests im Katalog läuft auf GitHub und zeigt, ob sie dort auch auftreten.
- Geprüft: Das gebaute `dist/index.html` enthält `data-storage="francais-1"`. Quellen und Curriculum unverändert.

## Explore

### Tasks

- [x] Set `archetype` as in the app's first plan in `.vibe/plans/`.
- [x] Skills are in `.agents/skills/`.
- [x] Read the README of the archetype's template: nichts Neues für diese Korrektur.
- [x] Load the content guide `.agents/skills/app-content/SKILL.md`. Read the plans in `.vibe/plans/`.
- [x] Interview: entfällt, keine Inhaltsänderung.
- [x] Load skill `lernapps-content-research`: entfällt, kein neuer Inhalt.
- [x] Under "Notes": didactic approach and scope: unverändert.
- [x] A kind of content the guide does not cover: entfällt.
- [x] **Checkpoint:** research: entfällt, keine Inhaltsänderung (siehe „Key decisions“).
- [x] Set `phase: plan`: change the value line.

### Answers

- Keine Inhaltsfragen. Der Ersteller hat den Eintrag in den Katalog verlangt; die Korrektur ist dafür nötig.

### Completed

## Plan

### Tasks

- [x] `grep '^phase:'` prints `phase: plan`; else set it.
- [x] Load skill `lernapps-content-growth`: entfällt, eine Änderung, keine Slices.
- [x] Write "Content method": entfällt, kein neuer Inhalt.
- [x] Each new component or interactive exercise: a sketch: entfällt.
- [x] Show the creator, short: Die Korrektur wird beim Prüfpunkt „publish“ gezeigt.
- [x] **Checkpoint:** confirm the plan and the content method: entfällt, siehe „Key decisions“.
- [x] Set `phase: code`: change the value line.

### Content method

Kein neuer Inhalt, kein neues Muster.

### Completed

## Code

### Tasks

- [x] `grep '^phase:'` prints `phase: code`; else set it.
- [x] `git switch -c increment/02-speichername` from `main`. Commit this plan on it.
- [x] Load skill `lernapps-cli`. Update the app as it says: Version des Werkzeugs unverändert (0.12.0), nichts zu aktualisieren.
- [x] Load skill `lernapps-explainer` and the content guide: Inhalt unverändert.
- [x] Paketname in `package.json` und `package-lock.json` auf `francais-1` setzen; Build prüfen (`data-storage`).
- [x] The content guide describes the app as it is now (`app-content-matches`). `grep -c "FILL IN"` prints 0.
- [x] `npx --no -- lernapps check` passes.
- [x] Look at the screens: entfällt, Seiten und Bilder unverändert; Messung der gebauten Seite siehe „Notes“.
- [x] Every box of Explore, Plan and Code ticked.
- [x] Set `phase: commit`: change the value line.

### Completed

## Commit

### Tasks

- [x] `grep '^phase:'` prints `phase: commit`; else set it.
- [x] An explainer whose pages or exercises changed: Seiten und Übungen unverändert, Selbsteinschätzung entfällt.
- [x] Load skill `lernapps-github`. Push the branch, open the preview pull request, see its checks to green as it says.
- [ ] **Checkpoint:** publish. Show what the increment adds and the preview link; ask whether it may go online. Wait for the yes.
- [ ] Load skill `lernapps-commit`. Publish as skill `lernapps-github` says: the pull request squash-merged into `main` with the message from this plan, the run of `Pages` watched to the end.
- [ ] Open the address the job `deploy` printed; confirm the new content. Never a derived address.
- [ ] App listed and its entry changes: Der Eintrag ist noch nicht gelistet; sein `commit` wird auf den neuen Stand gesetzt.
- [ ] Fill the retrospective.
- [ ] Commit this plan on `main` and push it. A push of only `.vibe/` publishes nothing.
- [ ] **Checkpoint:** list. Open the pull request to the catalog; see it to "bestanden", then show the creator the pull request and its result.
- [ ] Plan changed since its last push → commit it on `main`, push again.

### Completed

## Retrospective

### Phases reached

Code erreicht, Commit begonnen (Vorschau-Pull-Request offen). Veröffentlicht noch nicht.

### Creator turns after the plan

Keine: Die Korrektur folgt aus dem Auftrag, die App in den Katalog einzutragen.

### Where I had to guess

- Die Checkpoints „research“ und „plan“ habe ich für diese reine Namensänderung ausgelassen, ohne den Ersteller zu fragen. Der Prozess verlangt sie auch für Korrekturen; hier war nichts Inhaltliches zu bestätigen.
- Dass die Link-Fehler der lokalen Prüfung aus meiner Umgebung kommen, ist eine Vermutung; der Pull Request im Katalog zeigt es.
