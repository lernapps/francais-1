# Versuch: „À l'école – Mon premier jour“ (hoch autonomer Lauf)

Dieser Ordner ist ein Versuch und gehört nicht zur veröffentlichten App im Wurzelordner dieses Repositories.

Eine KI-Assistenz hat die App in etwa anderthalb Stunden Arbeit gebaut, mit einer simulierten Creatorin als Gegenüber. Danach haben ein Review, ein Lerner-Check und ein Durchgang der ganzen App Lücken gefunden, die behoben wurden. Der Ordner enthält die Inhalte der App und die Dateien, die den Lauf erklären:

- `src/`: der Inhalt als YAML (Kapitel `ecole`, sieben Seiten), `src/images/` (acht gezeichnete Figuren mit den Kindern Léa und Noé), `src/audio/` (38 Dateien mit KI-Stimmen).
- `.vibe/plans/01-schule-franzoesisch.md`: der Plan mit Entscheidungen, Antworten der Creatorin, Checkpoints, Notes zum Durchgang und Retrospektive.
- `.vibe/sketches/`: die zwei Skizzen, die die Creatorin bestätigt hat.
- `.agents/skills/app-content/SKILL.md`: der Inhaltsleitfaden der App, mit den Regeln, die aus den Fehlern des Laufs entstanden sind.
- `reviews/verdict-9e38652.yaml`: das Verdict des Reviews für den Commit `9e38652` (vor den Korrekturen).

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

Eine Geschichte in einem Schultag trägt die Seiten: Léa (10) und Noé (11), neu an einer Schule in Lyon, schreiben eine Postkarte an eine deutsche Partnerklasse. Beide sind auf Seite 1 vorgestellt und auf jeder Seite gezeichnet.

## Ausprobieren

Den Ordner `src/` über das `src/` eines frisch erzeugten Explainers kopieren (`rm -r src && cp -r versuche/ecole-autonomer-lauf/src src`), dann `npx --no -- lernapps check`.

## Was nicht geprüft ist

- Die 38 Audio-Dateien hat niemand angehört. Die Creatorin sollte jede anhören; ihre Freigabe ist ein Commit.
- Der Durchgang der ganzen App wurde nach den Korrekturen nicht wiederholt. Die neuen Texte auf den Seiten 2, 6 und 7 hat kein Sub-Agent gelesen.
- Die Links zur Lernkarte, die KMK-Standards und Zweitquellen wurden nicht geöffnet.
- Es gibt keine Selbsteinschätzung.
- Offene Hinweise des Reviews: Seite 6 hat mehrere neue Ideen auf einmal; die NC/SA-Lizenz der A1-Wortliste ist ungeklärt.

Die Zahlen zum Lauf stehen im Pull Request und auf der Beispielseite im Repository `lernapps/tooling`.
