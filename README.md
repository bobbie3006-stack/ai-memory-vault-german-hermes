# AI Memory Vault

> **This is a german fork while using Hermes-Agent instead of Cluade** Check [jaredrhod.com](https://jaredrhod.com) for Claude and/or English version of this repo.

**Läuft auf:** Entwickelt und getestet auf Claude Code - modifiziert für Hermes-Agent; jede Terminal-KI, die Dateien lesen und schreiben kann, funktioniert.

Verleihen Sie Ihrer KI ein echtes, dauerhaftes Gedächtnis. Dies ist das kostenlose, offene System, das einen Obsidian-Vault in das Arbeitsgedächtnis Ihrer KI verwandelt, sodass sie sich über Sitzungen hinweg an alles erinnert, außerhalb des Modells ohne Größenbeschränkung existiert und in einem Schritt genau das abruft, was sie benötigt. Kostenlos nutzbar, teilbar und weiterentwickelbar, auch kommerziell in Ihrem eigenen Unternehmen (siehe LIZENZ).

**Es wird außerdem mit meinem eigentlichen Agenten ausgeliefert.** Immer wieder wurde gefragt, ob man einfach meinen Jarvis herunterladen könne, anstatt einen Assistenten von Grund auf neu zu entwickeln. Deshalb ist er nun bereits in der Boot-Konfiguration enthalten: der Name, die Persönlichkeit, die Art, wie er spricht, und die Regeln, nach denen er arbeitet. Behalte ihn so, wie er ist, behalte ihn und ändere den Namen oder ersetze ihn durch deinen eigenen. Die Entscheidung liegt bei dir, und so oder so handelt es sich um einen Abschnitt in einer einzigen Datei.

## Die Installation

- **[ai-memory-vault.md](ai-memory-vault.md):** das Installationsskript. Führen Sie es im KI-Agenten (Claude, Hermes, etc.) aus, und es prüft, ob Obsidian überhaupt schon installiert ist (und installiert es gegebenenfalls für Sie), befragt Sie und erstellt dann ein vollständiges, sich selbst verwaltendes System: eine Boot-Konfiguration, eine Ordnerstruktur rund um Ihre tatsächlichen Projekte, tägliche Notizen, die sich von selbst schreiben, ein Profil, das sich aktualisiert, während die KI mehr über Sie lernt, und „Jobs“, die ihr beibringen, Ihre wiederkehrenden Aufgaben auf Ihre Art zu erledigen. Dein „Vault“ wird zum Gedächtnis der KI, sodass es außerhalb des Modells existiert und keine Größenbeschränkung hat; die KI speichert nur das, was für die aktuelle Aufgabe benötigt wird, und kann in einem Schritt auf alles andere zugreifen. Schau dir die Anleitung an: [https://www.youtube.com/playlist?list=PLN7lTYpeRLOc](https://www.youtube.com/playlist?list=PLN7lTYpeRLOc)

**Befindest du dich bereits in einer Agenten-Session?** Füge diesen Text ein, und das gesamte System wird gemeinsam mit dir aufgebaut: *„Ich möchte das einrichten: https://github.com/bobbie3006-stack/ai-memory-vault-german-hermes/ai-memory-vault.git“*

## AI Priming

Beim KI-Priming (AI Priming) lässt man seine KI zunächst eine bestimmte Auswahl seiner Notizen lesen, bevor sie die gewünschte Antwort oder Ausgabe liefert. Bevor mein Agent beispielsweise eine Marketing-E-Mail verfasst, liest er meine Notizen zum Texten, meine Notizen zum E-Mail-Marketing, mein Kundenprofil und meine Unternehmens-Wissensdatenbank. Erst dann beginnt er mit dem Schreiben. Das ist äußerst wirkungsvoll, denn bei der KI ist der Kontext entscheidend. Wenn Sie Ihre KI vor der Ausgabe mit dem erforderlichen Wissen und den nötigen Fähigkeiten „vorbereiten“, werden Ihre Ergebnisse stets besser und genauer ausfallen.

Jede Aufgabe erhält ihren eigenen Satz an Notizen. Eine E-Mail benötigt andere Notizen als eine Facebook-Anzeige. Der „Vault“ bewahrt alle Ihre Notizen an einem Ort auf und teilt Ihrer KI mit, welche Notizen sie für welche Aufgabe lesen soll. Sie richten das einmal ein, und Ihre KI bereitet sich danach bei jeder Aufgabe selbst vor.

Vollständige Definition und Beispiele: https://jaredrhod.com/ai-priming

## Vorlagen

Ausgangsdateien für das System. Jede Stelle, an der Ihre Angaben erforderlich sind, ist mit `[AUSFÜLLEN: ...]` gekennzeichnet. Legen Sie eine Vorlage ein und sagen Sie Ihrer KI: „Fülle das für mich aus“ – sie wird Sie dann befragen und den Text in Ihrem Stil verfassen (jede Vorlage enthält diese Anweisung für die KI). Oder füllen Sie die Vorlagen von Hand aus, wenn Ihnen das lieber ist.

- **[AGENT.md](templates/AGENT.md):** die Startkonfiguration. Sie kommt in den Ordner, von dem aus du deinen Agenten ausführst (dein **Arbeitsverzeichnis**), und wird **außerhalb deines Vaults** aufbewahrt, damit der Vault reine Notizen enthält und nicht durcheinandergerät, sobald du mehr als ein Projekt hast. Der Agent lädt sie bei jeder Sitzung automatisch und verweist die KI auf deinen Vault. Enthält die Identität deines Agenten (seinen Namen, seine Rolle und seine Persönlichkeit) sowie deine Startsequenz und die Regeln, die nicht außer Kraft gesetzt werden dürfen. **Diese Datei ist bereits einsatzbereit:** Die Identität meines eigenen Agenten ist bereits eingetragen und deutlich als der einzige Abschnitt gekennzeichnet, den du austauschen kannst, falls du lieber deinen eigenen haben möchtest.
- **[VAULT-INDEX.md](templates/VAULT-INDEX.md):** das Bedienungshandbuch. Diese Datei befindet sich **in deinem Vault** (es handelt sich um eine Notiz, keine Konfigurationsdatei). Dein Profil, deine Projekte, die vollständigen Vault-Regeln und wie du gerne mit der KI arbeitest.
- **[Tägliche Notiz-Vorlage.md](templates/Tägliche Notiz-Vorlage.md):** die Vorlage für die tägliche Notiz. Wird **in Ihrem Vault** unter `01 – Tägliche Notizen/Tägliche Notiz-Vorlage.md` abgelegt. Jede tägliche Notiz wird daraus erstellt, sodass das Protokoll ein einheitliches, übersichtliches Format behält.
- **[MEMORY.md](templates/MEMORY.md):** Der Zeiger auf den eigenen Speicher von der Agenten-Lösung. Er wird im **Projektordner von Claude Code/Hermes-Agent** (`~/.claude/projects/...`, `~/.hermes/memories/MEMORY.md`, nicht in Ihrem Vault) abgelegt. Er leitet den nativen Speicher zurück in den Vault um, sodass niemals zwei Speicherebenen entstehen, die voneinander abweichen.

## Aktualisierung

Das Build-Skript, die Vorlagen und der Assistent werden kontinuierlich verbessert. Wenn Sie eine Kopie dieses Repos auf Ihrer Festplatte gespeichert haben, geben Sie Ihrem Agent beispielsweise folgenden Befehl: **„Lade die neueste Version von ai-memory-vault herunter und teile mir mit, was sich geändert hat.“** Aktualisierungen betreffen ausschließlich die Dateien des Repos selbst. Dein Vault, deine Notizen und deine CLAUDE.md gehören dir und befinden sich niemals in diesem Repo, sodass nichts, was du erstellt hast, überschrieben werden kann. Über fullstack-agent installiert? `./fullstack-agent/update.sh` aktualisiert alle Teile auf einmal und gibt aus, was sich geändert hat.

## Der Rest

Ein Verstand ist besser mit einem Mund, einem Gesicht und Händen. Sobald sich dein Agent an dich erinnert, sind die nächsten logischen Schritte, laut mit ihm zu sprechen, ihm ein Gesicht auf dem Bildschirm zu geben und deine Notizen mit bloßen Händen zu verschieben.

- **Der gesamte Stack – mit einem einzigen Befehl.** [fullstack-agent](https://github.com/jaredrhod/fullstack-agent) installiert den Speicher, die Sprachfunktion, die Gesichtserkennung und die Handgesten und verbindet sie für Sie miteinander. Wählen Sie einfach die Komponenten aus, die Sie benötigen: https://jaredrhod.com
- **Die Videos.** Kostenlose Serie zu all diesen Themen: https://youtube.com/@jaredrhod
- **Der Discord.** Tausende von Entwicklern und der schnellste Weg, um aus einer Sackgasse herauszukommen: https://discord.gg/YSdsqMv3V8
- **Alles andere,** kostenlos und offen: https://jaredrhod.com

## Unterstützung

Die Nutzung ist kostenlos und wird es auch immer bleiben. Wenn dir das weitergeholfen hat, kannst du mir einen Kaffee spendieren:

[![Unterstütze mich auf Ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/jaredrhod)

## Lizenz

Copyright (c) 2026 Jared Rhodenizer.

Licensed under Creative Commons Attribution-ShareAlike 4.0 International (CC BY-SA 4.0). **Use it in your business, commercially, for free.** Copy it, adapt it, and build your own system on it. Two rules: credit me, and license your own adapted version the same way so the next person gets what you got. Full terms are in the LICENSE file and at https://creativecommons.org/licenses/by-sa/4.0/
