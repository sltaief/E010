[1]: https://www.tuxcademy.org/download/de/lxk1/lxk1-de-manual.pdf#chapter.582


# Scheduler
Scheduler sind dazu da, einmalige oder wiederkehrende Aufgaben (Jobs) zu einem bestimmten Zeitpunkt auszuführen.
Unter Unix sind folgende Tools dafür geeignet.

+ cron - für wiederkehrende Jobs
+ at - für einmalige Jobs


## cron

Einen Cron Eintrag zu definieren ist relativ einfach, folgende Grafik zeigt den Syntax.

![Image](../../images/crontab.png)

Ein `*` beduetet, dass jedes Ereignis zutrifft. Jeder Wert kann mit Komma getrennt, mehrfach definiert werden.

|Feld|Beschreibung|mögliche Werte|
|:--:|:--:|:--:|
|1 |Minuten | 0-59 |
|2 |Stunden |0-23 |
|3 |Tag im Monat |1-31|
|4 |Monat |1-12|
|5 |Tag in der Woche|0-6 (Start mit Son 0, Mon 1 usw..) |
|6 |Command | Kommando das ausgeführt wird|

Beispiel: Führt das Kommando von Montag bis Freitag zwichen 07:00 bis 17:00 jewiels alle 10 Minuten aus.

`0,10,20,30,40,50 07-17 * * 1-5 /path/command`

Anstelle von `0,10,20,30,40,50` kann auch die Notation `*/10` verwendet werden

`*/10 * * 1-5 /path/command`

### Cron Beispiele

Job zweimal am Tag starten (11 und 16 Uhr)

`00 11,16 * * * Command`

Job um spezifische Zeit starten (08. Juni 14:15)

`15 14 08 06 * Command`

Job stündlich während Bürozeiten starten (Mo-Fr 07:00 bis 17:00)

`00 07-17 * * 1-5 Command`

Immer am ersten Sonntag im Monat. Hier ist etwas Skripten nötig. Wenn beide für die Tage relevanten Felder (Day of Week und Day of Month) verwendet werden, nimmt Cron den ersten zutreffenden. Um das zu lösen, stellen wir Cron so ein, dass jeweils die ersten 7 Tage im Monat (und somit sicher auch ein Sonntag) gültig sind. Um nun den Sonntag aus diesen 7 Tagen zu finden, benützen wir etwas shell-Skript, dass nun den Kommand nur ausführt ( `&&` ), wenn der Wochentag *0* ist, was Sonntag entspricht.

`0 05 1-7 * * [ "$(date '+\%w')" -eq "0" ] && Command`

### Crontabs editieren

Crontab des aktuellen User editieren

`crontab -e`

Crontab eines bestimmten Useres editieren (sofern berechtigt)

`crontab -e -u <user>`

### Crontab anzeigen

Crontab des aktuellen (eingeloggten) User anzeigen

`crontab -l`

Crontab eines bestimmten Useres anzeigen

`crontab -l -u <user>`

## at

at Job definieren

`at -t 180606193000 -f /path/command`

Job Queue listen

`atq`

Job Informationen zu einem Job

`at -c <id>`

Job löschen

`at -d <id>`

## Berechtigungen (at & cron)
Die Berechtigungen ob ein User einen at- oder cron Job ausführen darf, wird über folgende Berechtigungsdateien gesteuert, wobei das Vorgehen für at und cron identisch ist.

Für cron:
+ /etc/cron.allow
+ /etc/cron.deny

Für at:
+ /etc/at.allow
+ /etc/at.deny

Ist eine allow Datei vorhanden, so **muss** jeder User der Jobs ausführen darf in der Datei eingetragen sein. Ist keine allow Datei vorhanden, was der Standard ist, dann würd geprüft, ob ein User in der deny Datei von der Ausführung ausgeschlossen ist. Ist also keine allow Datei vorhanden und in der deny Datei kein User Eintrag, so darf jeder Jobs mittels cron oder at Schedulen.


## wichtige Befehle
|Befehl | Bedeutung|
|:--:|--|
|crontab|Cron Einträge listen oder editieren|
|at| Job definieren|
|atq| Jobs listen|


## wichtige Files und Verzeichnisse
|File/Dir | Bedeutung|
|:--:|--|
|/var/spool/cron| Ablageort der cron-Jobs|
|/var/spool/at| Ablageort der at-Jobs|
|/var/log/cron|Logfile der Cronjobs|
| /etc/cron.allow |definiert wer cron Jobs ausführen darf|
| /etc/cron.deny| definiert wer keine cron Jobs ausführen darf|
| /etc/at.allow |definiert wer at Jobs ausführen darf|
| /etc/at.deny| definiert wer keine at Jobs ausführen darf|

## weitere Infos
mehr zu diesem Thema finden sie [hier][1]
