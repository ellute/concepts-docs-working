---
status: aktiv
owner: Enrique
updated: 2026-10-14
---

# Konventionen

Regeln für dieses Repo. Gelten für alle, die hier schreiben – Menschen und Claude.
Wer etwas ändern will: PR auf diese Datei.

## Grundprinzip

GitHub ist die einzige Quelle für Inhalte.
Planner verwaltet Aufgaben und verlinkt nur auf Dateien oder PRs in diesem Repo.
Word/PDF für Externe werden aus dem Markdown erzeugt und nicht separat gepflegt.

## Ablauf

1. Vor dem Arbeiten: `main` aktualisieren (`git pull`).
2. Eigenen Branch erstellen – nie direkt auf `main` arbeiten.
3. Committen, Branch pushen, Pull Request öffnen.
4. PR prüfen und mergen – wenn möglich durch eine zweite Person.
5. Branch nach dem Merge löschen.

`main` ist durch ein Ruleset geschützt: kein direkter Push, kein Force-Push, PR zwingend.
Zurzeit ist keine formelle Freigabe nötig (Required approvals: 0); sobald Kollegen mitarbeiten, auf 1 erhöhen.

## Branch-Namen

`<wer>/<thema>`, nur Kleinbuchstaben und Bindestriche.

- `enrique/followup-sams`
- `claude/conventions`

## Ordner und Dateien

```
docs/            Inhalte, ein Thema pro Datei
docs/_vorlage.md Vorlage für neue Dokumente
CONVENTIONS.md   diese Datei
README.md        Einstieg
```

- Dateinamen: Kleinbuchstaben, Bindestriche, keine Umlaute oder Leerzeichen – `kunde-a-onboarding.md`.
- Ein Thema pro Datei. Wird eine Datei zu lang, aufteilen.
- Unterordner erst anlegen, wenn es mehr als ca. zehn Dateien zum selben Bereich gibt.

## Aufbau eines Dokuments

Jedes Dokument beginnt mit einem Kopfbereich:

```yaml
---
status: entwurf | aktiv | archiviert
owner: Name
updated: JJJJ-MM-TT
planner: <Link zur Planner-Aufgabe, optional>
---
```

- `updated` bei jeder inhaltlichen Änderung anpassen.
- Eine `#`-Überschrift pro Datei (Titel), darunter `##` und `###`.
- Überschriften stabil halten – nicht ohne Grund umbenennen.
- Ein Satz pro Zeile oder kurze Absätze. So zeigen Diffs genau, was sich geändert hat.
- Offene Punkte als `- [ ] ...` markieren.

## Was nicht ins Repo gehört

- Passwörter, Tokens, Lizenzschlüssel
- Echte Kunden- oder Personendaten (in diesem Übungsrepo generell keine echten Firmeninhalte)
- Binärdateien wie .docx oder .xlsx – stattdessen Markdown oder ein Link

Git-Historie vergisst praktisch nie. Was einmal committet ist, bleibt auffindbar.

## Commit-Nachrichten

Kurz, im Imperativ, auf Deutsch: `Follow-up-Liste ergänzen`, `Tippfehler in Onboarding korrigieren`.

## Zusammenarbeit mit Claude

- Aufgabe mit Dateipfad geben, z.B. «Aktualisiere `docs/kunde-a-onboarding.md` mit …».
- Claude arbeitet auf einem Branch `claude/<thema>` und öffnet einen PR mit Zusammenfassung.
- Review und Merge macht immer ein Mensch.
- Dateien, die du gerade lokal offen und noch nicht gepusht hast, nicht gleichzeitig Claude übergeben.
