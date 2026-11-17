# Versuch: „À l'école – Mon premier jour“ (hoch autonomer Lauf)

Dieser Ordner ist ein Versuch und gehört nicht zur veröffentlichten App im Wurzelordner dieses Repositories.

Eine KI-Assistenz hat die App in etwa einer Stunde gebaut, mit einer simulierten Creatorin als Gegenüber. Der Ordner enthält die Inhalte der App und die Dateien, die den Lauf erklären:

- `src/`: der Inhalt als YAML (Kapitel `ecole`, sieben Seiten), `src/images/` (sieben gezeichnete Figuren), `src/audio/` (KI-Stimmen).
- `.vibe/plans/01-schule-franzoesisch.md`: der Plan mit Entscheidungen, Antworten der Creatorin, Checkpoints und Retrospektive.
- `.vibe/sketches/`: die zwei Skizzen, die die Creatorin bestätigt hat.
- `.agents/skills/app-content/SKILL.md`: der Inhaltsleitfaden der App.

## Inhalt

| Seite | Kompetenz der Lernkarte |
|---|---|
| `artikel-bestimmt` | `bestimmter-artikel` |
| `zahlen` | `zahlen-bis-100` |
| `artikel-unbestimmt` | `unbestimmter-artikel` |
| `uhrzeit` | `uhrzeit` |
| `datum` | `datum-wochentage-monate` |
| `schule` | `schule-und-schulalltag` |
| `alltagstexte` | `alltagstexte` |

Eine Geschichte trägt die Seiten: Léa und Noé schreiben als neue Kinder einer Schule in Lyon eine Postkarte an eine deutsche Partnerklasse.

## Ausprobieren

Den Ordner `src/` über das `src/` eines frisch erzeugten Explainers kopieren (`rm -r src && cp -r versuche/ecole-autonomer-lauf/src src`), dann `npx --no -- lernapps check`.

## Was nicht geprüft ist

- Die 38 Audio-Dateien hat niemand angehört. Die Creatorin sollte jede anhören; ihre Freigabe ist ein Commit.
- Nur Seite 1 hat einen Lerner-Check durch einen Sub-Agenten im Browser. Die Seiten 2 bis 7 sind nur mit `lernapps check` und Bildschirmfotos der Figuren geprüft.
- Die Links zur Lernkarte, die KMK-Standards und Zweitquellen wurden nicht geöffnet.
- Es gibt keine Selbsteinschätzung.

Die Zahlen zum Lauf stehen im Pull Request und auf der Beispielseite im Repository `lernapps/tooling`.
