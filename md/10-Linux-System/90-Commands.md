# Commands

Hier sind alle im W901 verwendeten Kommandos alphabetisch gelistet.

> [root@w901 /]# sort -k 1 -t ';' lnx_cmd |uniq |awk -F";" '{print "|"$1"|"$2"|"}'

|Befehl | Bedeutung|
|:--:|--|
|at| at Jobs definieren|
|atq| Zeigt at Jobs Queue|
|awk| Beliebiges Manipulieren von Textdateien - sehr mächtig|
|bg| Prozess in Background|
|chmod| Berechtigungen ändern|
|chown| Ownership ändern|
|crontab| Crontab editieren und anzeigen|
|cut| Schneidet bestimmte Teile aus den Zeilen einer Datei aus|
|df| Zeigt freier Speicherplatz|
|dmesg| zeigt Kernel Messages vom Bootprozess an|
|du| Zeigt belegter Speicherplatz|
|e2fsck|Filesystemcheck|
|fdisk|Disk Partitions Utillity|
|fg| Prozess in Vordergrund|
|file| Zeigt Filetype an|
|find| Suchen von Dateien und Verzeichnissen|
|grep| Strings suchen|
|head| List eine Datei vom Beginn |
|id| zeigt User ID|
|jobs| zeigt Jobs im Background|
|journalctl| Zeigt Messages vom systemd Logdaemon an|
|last| zeigt letzte User Logins und Systemreboot an|
|less| Analog more, jedoch ohne User Interaktion (Security)|
|logger| Kommando zum schreiben von Logeinträgen|
|ls| Listet Files und Directory|
|lspci|Listet PCI Devices auf|
|lsusb|listet USB Devices auf|
|lvcreate| lvm - logical Volume erzeugen|
|lvdisplay| lvm - Attribute von logical Volumes listen|
|lvresize| lvm - logical Volume Grösse anpassen|
|lvs|lvm - Informationen über logical Volumes|
|man| Manual pages|
|mkfs|Filesystem erzeugen|
|more| Gibt Textdatei pageweise aus|
|mount| Filesystem einhängen - oder anzeigen was eingehängt ist|
|nohup| führt Prozess nach Beenden der Session weiter|
|pstree| Zeigt Prozesse in Baumstruktur|
|ps| Zeigt Prozessliste|
|pvcreate| lvm - physical Volume erzeugen|
|pvdisplay| lvm - Attribute von physical Volumes listen|
|pvs|lvm - Informationen über physical Volumes|
|resize2fs|Filesystem Grösse anpassen|
|rpm| Packet Manager|
|sort| Sortieren von Ausgaben|
|strings| Ausgabe von printbaren Charakter|
|sudo| Befehl mit sudo Berechtigungen ausführen|
|tail| List eine Datei vom Ende|
|top| Dynamische Anzeige Prozessinformationen|
|umask| Standard Berechtigungen bei neuen Files|
|umount| Filesystem abhängen|
|uniq| Entfernen von Duplikation in Ausgaben|
|vgdisplay| lvm - Attribute von Volumes Groups listen|
|vgs| lvm - Informationen über Volumes Groups|
|visudo| Editor für SUDO Definition (sudoers) mit Syntax Prüfung|
|which| Zeigt wo ein Binary abgelegt ist (geht nur für Suchpfad)|
|yum| Software Manager|
