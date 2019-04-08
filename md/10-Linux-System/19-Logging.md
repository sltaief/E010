[1]: https://www.tuxcademy.org/download/de/lxk1/lxk1-de-manual.pdf#chapter.611


# Logging

## syslog / rsyslog - das klassische Logging

**Syslog** ist der standard Logger unter Unix. Die Konfiguration wird in `/etc/syslog.conf` oder`/etc/rsyslog.conf` definiert.

###  Die Syslog Levels
Syslog Meldungen können nach verschiedenen Kritikalität erstellt werden.

|Nr.|Level| Beispiel|
|:--:|:--:|:--|
|0 | Emergency | system is unusable|
|1 | Alert | action must be taken immediately|
|2 | Critical | critical conditions|
|3 | Error | error conditions|
|4 | Warning | warning conditions|
|5 | Notice | normal but significant condition|
|6 | Informational | informational messages|
|7 | Debug|  debug-level messages |

## logrotate
Die Logfiles wachsen ständig an. Würde kein *Housekeeping* stattfinden so würde früher oder später eine Festplatte volllaufen. Um das zu verhindern, führt das `logtotate` Programm über Cron gesteuert regelmässig ein *Housekeeping* der Logfiles durch. Dabei können Logfiles archiviert, komprimiert und auch gelöscht werden. In der Konfigurationsdatei `/etc/logrotate.conf` wird Logtotate definiert.

## dmesg
Mit dem Kommando `dmesg` werden Kernel Meldungen des Bootvorgangs angezeigt. Das kann sehr nützlich sein, wenn Informationen über Hardware Treiber oder sonstiger Hardwre benötigt werden.


## Journalctl - das neue Logging von systemd

Journalctl kann alles was syslog kann. Es ist ein neur Ansatz und wird irgendwann syslog komplett ersetzen. Journalctl und Syslog können problemlos parallel betrieben werden. Wir gehen hier nicht weiter auf jornalctl ein, da aktuell in der Praxis noch immer syslog weiterverbreitet ist. Trotzdem lohnt es sich durchwegs, einmal genauer zu schauen was journalctl kann.


## logger - Logmessages schreiben

Mit dem Kommando `logger` könne Meldungen in die Logfiles geschrieben werden

### Beispiele
Eine Meldung ins /var/log/message schreiben

`logger some-text`

schreibt einen Logeintrag inklusive Prozessid (-i) ins /var/log/mail
`logger -i -p mail.err "Oh Noes"`



## wichtige Befehle

|Befehl | Bedeutung|
|:--:|--|
|last| Zeigt letzte User Logins und Systemreboot an|
|journalctl | Listet Eintäge aus systemd-journald|
|dmesg| Kernel Meldungen|
|logger| Meldungen in Logfiles schreiben|

## wichtige Files und Verzeichnisse
|File/Dir | Bedeutung|
|:--:|--|
|/etc/rsyslog.conf| Konfiguration Datai für syslog|
|/var/log/messages| Standard Logdatei|
|/var/log/wtmp| Binär Datei mit Logging Informationen|
|/etc/logrotate.conf| Konfiguration Logrotate|

## weitere Infos
mehr zu diesem Thema finden sie [hier][1]
