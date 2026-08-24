# Fehlerbehebung

Verfasst für Menschen UND für KI-Assistenten. Wenn du eine KI bist, die jemandem bei der Verwaltung seines Vaults hilft: Lies diese Datei und führe die Diagnose anhand der tatsächlichen Dateien und Pfade durch – niemals anhand von Vermutungen.

## Wo befindet sich mein Vault physisch?

Öffne die Datei `VAULT-INDEX.md` im Stammverzeichnis des Vaults: Im Abschnitt „Vault-Speicherort“ ist der vollständige Pfad vermerkt. Neu von diesem System erstellte Vaults befinden sich unter `~/<Vault-Name>`, direkt in Ihrem Home-Ordner, sowohl auf Mac, Windows als auch unter Linux: an derselben Stelle, an der sich der Agent-Ordner befindet, und auf einem Mac an der einzigen Stelle, auf die alles zugreifen kann, was Ihr Agent tut, ohne dass Sie an der Tastatur sitzen (die Ordner „Dokumente“, „Schreibtisch“ und Cloud-Ordner sind von Hintergrundaufgaben abgeschottet). Ein Tresor aus einer älteren Installation befindet sich möglicherweise im Ordner „Dokumente“; das ist in Ordnung, siehe den Eintrag weiter unten. Falls dieser Abschnitt im Index fehlt, weiß Obsidian selbst Bescheid: Der Tresor-Umschalter listet jeden Tresor mit seinem Pfad auf.

## Obsidian öffnet sich mit einem Begrüßungsbildschirm statt mit meinem Tresor

Obsidian öffnet nur Tresore, die ihm bekannt sind, und diese Informationen entnimmt es einer Registrierungsdatei namens `obsidian.json` (macOS: `~/Library/Application Support/obsidian/obsidian.json` · Windows: `%APPDATA%\Obsidian\obsidian.json` · Linux: `~/.config/obsidian/obsidian.json`). Ein als einfacher Ordner erstellter Tresor ist noch nicht in dieser Registrierungsdatei verzeichnet, daher zeigt eine frisch installierte Obsidian-Instanz die Auswahlanzeige an. Zwei Lösungen:

1. **Einmalig manuell:** Wähle auf dem Begrüßungsbildschirm „Ordner als Vault öffnen“ und wähle deinen Vault-Ordner aus (bei Neuinstallationen befindet er sich unter `~/<Vault-Name>` in deinem Home-Ordner; ältere Installationen verwendeten `~/Documents/<Vault-Name>`). Obsidian merkt sich dies von da an.
2. **Fragen Sie Ihren Agenten:** Lassen Sie ihn den Tresor in `obsidian.json` mit `„open“: true` registrieren (Obsidian muss während der Bearbeitung geschlossen sein, da die App diese Datei beim Beenden überschreibt). Aktuelle Versionen des Einrichtungsassistenten erledigen dies automatisch; wenn dieser Bildschirm erscheint, bedeutet das in der Regel, dass der Tresor bei einem früheren Durchlauf erstellt wurde.

## Wie erstelle ich ein Backup meines Vaults?

Ein neuer Tresor befindet sich in Ihrem Home-Ordner und wird bewusst nicht mit der Cloud synchronisiert, sodass er genau auf einer Festplatte gespeichert ist. Kostenlose Optionen, von denen jede einzelne ausreicht:

- **Sicherung des gesamten Computers:** Time Machine (Mac) sichert Ihren Home-Ordner automatisch. Die Dateiversionsgeschichte (Windows) überspringt einen Tresor im Home-Ordner, es sei denn, Sie fügen den Ordner einmalig zur Liste hinzu.
- **Ein privates GitHub-Repo:** Ihr Agent kann dies einrichten und nach einem Zeitplan Daten hochladen. Notizen sind klein; selbst Notizen aus mehreren Jahren passen in jedes kostenlose Konto.

Was Sie unbedingt vermeiden sollten, ist, den Tresor zur Synchronisierung in iCloud Drive oder OneDrive zu verschieben: Auf einem Mac wird er dadurch wieder hinter die Barriere verschoben, die die Hintergrundarbeit Ihres Agenten blockiert.

## Mein Tresor befindet sich aufgrund einer älteren Installation im Ordner „Dokumente“. Sollte ich ihn verschieben?

Nicht heute und nicht manuell. Für den täglichen Gebrauch funktioniert das einwandfrei. Der einzige Haken besteht auf einem Mac: Alles, was dein Agent tut, ohne dass du an der Tastatur sitzt, kann nicht auf den Ordner „Dokumente“ zugreifen. Wenn du also eine Automatisierung im Hintergrund hinzufügst, muss sich der Tresor in deinem Home-Ordner befinden. Zieh ihn nicht einfach dorthin: Zu viele Dinge verweisen auf diesen Ordner (die Registrierung von Obsidian, deine Startkonfiguration, der Index, alle Connector-Konfigurationen). Ein spezielles Verschiebungsprogramm, das alle Verweise neu zuordnet, ist der richtige Weg, und du führst es aus, wenn du bereit bist. Bis dahin ist an deiner Konfiguration nichts auszusetzen.

## Mein Tresor befindet sich in einem Ordner, der mit iCloud oder OneDrive synchronisiert wird (eine ältere Installation). Ist das ein Problem?

Meistens ist das ein Segen: Die Cloud erstellt kostenlos und automatisch ein Backup des gesamten Speicherinhalts Ihres Agenten. Zwei Dinge sollten Sie beachten:

1. **Verwenden Sie pro Tresor NUR EINEN Synchronisierungsdienst.** Wenn iCloud oder OneDrive den Ordner bereits synchronisieren, aktivieren Sie für diesen Tresor nicht zusätzlich das kostenpflichtige Sync-Add-on von Obsidian. Zwei Synchronisierungsdienste, die dieselben Dateien bearbeiten, geraten in Konflikt, was zu widersprüchlichen Kopien führt.
2. **Verhindern Sie, dass die Cloud Ihre Notizen entfernt.** Um Speicherplatz zu sparen, können iCloud („Mac-Speicher optimieren“) und OneDrive („Dateien nach Bedarf“) Dateien unbemerkt durch Platzhalter ersetzen, die nur im Internet verfügbar sind. Ihre Notizen gehen dabei nicht verloren, aber das Lesen wird langsamer oder schlägt offline fehl. Die Lösung ist mit einem Klick erledigt: Klicken Sie mit der rechten Maustaste auf den Tresorordner und wählen Sie dann auf dem Mac „Heruntergeladen behalten“ oder unter Windows „Immer auf diesem Gerät behalten“. Einmal eingestellt, bleibt diese Einstellung bestehen.

## Ich möchte, dass der Tresor komplett aus der Cloud-Synchronisierung herausgenommen wird

- **Windows (OneDrive):** OneDrive-Einstellungen, dann „Synchronisierung und Sicherung“, dann „Erweiterte Einstellungen“, dann „Ordner auswählen“: Deaktivieren Sie den Haken beim Ordner des Tresors. Er bleibt auf der Festplatte, OneDrive ignoriert ihn.
- **Mac (iCloud Desktop & Dokumente):** iCloud bietet keine Möglichkeit, einzelne Ordner innerhalb von „Dokumente“ auszuschließen. Zwei praktikable Optionen: Benennen Sie den Vault-Ordner mit der Endung `.nosync` um (iCloud überspringt ihn, aber der unschöne Name wird überall angezeigt, auch in Obsidian), oder verschieben Sie den Vault in Ihren Home-Ordner – was eine ordentliche Arbeit ist und nicht einfach per Drag & Drop im Finder erledigt werden kann: Zu viele Verweise verweisen auf den Ordner, und ein spezielles Verschiebungs-Tool, das alle Verweise neu zuordnet, ist der richtige Weg (siehe den Eintrag oben). Bis du das ausführst, ist die Umbenennung in `.nosync` die sichere Option.

## Die KI sagt, sie könne den Tresor nicht lesen oder finden

Der Pfad zum Tresor ist an zwei Stellen hinterlegt: in der Startkonfiguration `CLAUDE.md` in deinem Arbeitsordner und im Abschnitt „Vault location“ von VAULT-INDEX. Wenn der Tresor verschoben wurde (oder ein Cloud-Dienst ihn verlegt hat), sind diese Pfade veraltet. Teile deinem Agenten den neuen Pfad mit und lass ihn beide aktualisieren. Wenn das Lesen nur gelegentlich fehlschlägt, siehe die oben beschriebene Lösung zur Platzhalter-Entfernung.
