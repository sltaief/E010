[1]: https://www.tuxcademy.org/download/de/lxk1/lxk1-de-manual.pdf#chapter.272
[2]: https://www.grund-wissen.de/linux/linux-dateisystem.html
# das Linux Filesystem

## Aufbau

das Linux Filesystem beginnt immer im Worzelverzeichnis, dem *root* resp. */* . Alle weiteren
Verzeichnise basieren auf diesem Rootverzeichnis.

Für einen **„normalen“ Benutzer** ist vor allem das **Home-Verzeichnis** von Bedeutung, das häufig mit ~ abgekürzt und unter dem Verzeichnis-Pfad /home/benutzername abgelegt ist.

Mit `cd ~` Wechsel ins eigene Home-Verzeichnis.

Mit `cd -` wird auf das zuletzt verwendete Verzeichnis gewechselt.

Innerhalb dieses Verzeichnisses kann der Benutzer beliebige weitere Verzeichnisse anlegen und/oder Dateien speichern. Eine Besonderheit unter Linux ist die Kenntlichmachung von Konfigurations-Dateien und -Verzeichnissen: Diese beginnen stets mit einem . (Punkt) vor dem eigentlichen Dateinamen; man bezeichnet sie bisweilen auch als **„versteckte“** Dateien, da sie beispielsweise bei einem Aufruf der ls-Anweisung in einer Shell standardmäßig nicht mit aufgelistet werden.

## Permission
Ein **x** bei den Verzeichnis Permission beduetet nicht, dass ein Verzeichnis ausgeführt werden kann (Verzeichnise können nicht ausgeführt werden), es bedeutet, dass ein **Wechsel** oder **travers** in das Verzeichnis erlaubt ist.

Hier darf nur der User *root* oder die Member der Gruppe *root* in das Verzeichnis wechseln.
> dr-xr-x---.   2 root root  135 May 23 12:57 root

### Linux Filesystem Struktur
![Image](../../images/linux-file-structure.png)

|Verzeichnis|Verwendung|
|:--:|--|
|/|Das Verzeichnis / (auch „Wurzelverzeichnis“ oder „root“ genannt) stellt den Basispfad des Systems dar.|
|/bin| In diesem Verzeichnis („binaries“) befinden sich wichtige Programme für Anwender, die immer verfügbar sein müssen, beispielsweise die Shell bash oder das Programm ls zur Anzeige von Verzeichnis-Inhalten.|
|/boot|In diesem Verzeichnis befinden sich die zum Hochfahren des Systems unbedingt erforderlichen Dateien. Am wichtigsten ist dabei der Kernel, üblicherweise eine Datei mit dem Namen vmlinuz-versionsname (andere Namen sind ebenfalls möglich).|
|/dev|n diesem Verzeichnis („devices“) befinden sich ausschliesslich Geräte-Dateien. Diese speziellen Dateien stellen eine einfach nutzbare Schnittstelle zur Hardware dar. Für jede Festplatte und ihre Partitionen existiert im /dev/-Verzeichnis ein eigener Eintrag. Beispielsweise bezeichnet, sofern vorhanden, /dev/hda ist die erste IDE-Festplatte, /dev/sda die erste SCSI-Festplatte im System. Höhere Buchstaben (sdb, sdc) stellen weitere Festplatten oder externe Speichermedien dar, Zahlen am Ende (sda1, sda2) benennen die Partitionen der Festplatten. |
|/etc|In diesem Verzeichnis („etcetera“) befinden sich zahlreiche Konfigurationsdateien, die Einstellungen zu den installierten Programmen sowie grundlegende Systeminformationen enthalten; viele dieser Dateien haben eigene Manpage, die in einer Shell mittels eines Aufrufs der Form man /etc/fstab aufgerufen werden kann.|
|/home|In diesem Verzeichnis befinden sich die persönlichen Verzeichnisse der einzelnen Benutzer.|
|/lib|In diesem Verzeichnis („libraries“) befinden sich die wichtigsten Funktionsbibliotheken des Systems; diese Dateien sollten nicht manuell verändert werden.|
|/media|In diesem Verzeichnis werden externe Datenträger als Unterverzeichnisse eingebunden. Bei aktuellen Ubuntu- und LinuxMint-Versionen werden automatisch erkannte USB-Sticks, Speicherkarten, externe Festplatten usw. in ein Verzeichnis der Art /media/benutzername/name-des-datentraegers eingebunden.|
|/proc|In diesem Verzeichnis („processes“) sind keine gewöhnlichen Dateien enthalten, sondern Schnittstellen zum Linux-Kernel. Jedes laufende Programm wird hier in einem Unterverzeichnis geführt, dessen Dateien viele Informationen beispielsweise über den aktuellen Programmstatus enthalten.|
|/root|In diesem Verzeichnis befinden sich die (persönlichen) Dateien des Systemverwalters („Root“, „Superuser“). Das Verzeichnis liegt im Wurzelverzeichnis, damit der Systemverwalter auch dann auf seine (Konfigurations-)Dateien zugreifen kann, wenn durch einen Fehler der Zugriff auf andere Partitionen nicht mehr möglich ist. |
|/sbin|In diesem Verzeichnis („superuser-binaries“) befinden sich ebenfalls – ähnlich wie im /bin-Verzeichnis – wichtige Programme, die allerdings für den Systemverwalter gedacht sind. Sie erfüllen Funktionen, auf die ein normaler Benutzer keinen Zugriff hat.|
|/tmp|Dieses Verzeichnis („temporary“) kann von jedem Benutzer und jedem Programm als temporäre Ablage für Dateien verwendet werden.|
|/usr|In diesem Verzeichnis („unix system ressources“) befinden sich der grösste Teil der installierten Software. Auf vielen Systemen befinden sich innerhalb von /usr mehr Daten als in allen anderen Dateien zusammen. Die ausführbaren Programmdateien sind meist in /usr/bin, Programmbibliotheken in /usr/lib abgelegt.|

[Quelle www.grund-wissen.de][2]

## wichtige Befehle
|Befehl | Bedeutung|
|:--:|--|
|mount|zum einhängen/aushängen und anzeigen von eingegängten Filesystemen|
|du|Belegter Speicherplatz|
|df|Feier Speicherplatz|


## wichtige Files
|File | Bedeutung|
|:--:|--|
|/etc/fstab|Definition der Filesystem welche (zu boot time) eingehängt werden|

## weitere Infos
mehr zu diesem Thema finden sie [hier][1]
