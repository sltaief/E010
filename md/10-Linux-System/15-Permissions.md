[1]: https://www.tuxcademy.org/download/de/lxk1/lxk1-de-manual.pdf#chapter.367
[2]: http://permissions-calculator.org/
[3]: https://www.garron.me/en/go2linux/ls-file-permissions.html
# Permission

## File und Directory Ownership

### chown

Jedes File und Verzeichnis gehört einem  *Owner* und einer *Gruppe*. Die entsprechenden
Ownership sind mit `ls -l` ersichtlich.

Zum ändern der Ownership wird `chown <user>:<gruppe> datei` verwendet.

Beispiel: File Ownership von *textfile.txt* auf bem:root ändern

`chown bem:root textfile.txt`

## File und Directory Permission

### chmod

Jedes File und Verzeichnis hat prinzipiel für den **Besitzer** , die **Gruppe** und der ganze **Rest**, oder besser bekannt unter **Owner, Group und Others** entsprechende Berechtigungen.

Für jeden erwähnten Typ kann jeweils *eines*, *keines* oder *mehrere* der folgenden Rechte (Permission) vergeben werden.

|permission|mit *ls* angezeigt als|octal|
|:--:|:--:|:--:|
|read|r|4|
|write|w|2|
|execute|x|1|

Zum Ändern der Permission wird `chmod <permission> <file/dir>` verwendet

Beispiele:

`chmod u+rwx <datei>` gibt dem User read,write und execute Rechte, alle andern Rechte bleiben unverändert

`chmod ug+x <datei>` gibt dem User und der Gruppe execute Rechte, alle andern Rechte bleiben unverändert

`chmod o-rw <datei>` entzieht Others die lese und schreib Rechte, alle andern Rechte bleiben unverändert

`chmod 755 <datei>` setze read,write,exectue für User und je read,execute für Group und others

`chmod 640 <datei>` setzt read,write für User, read für Group und keine Rechte für Others

Zum Üben mit den Permission und den verschiednene Schreibweisen eigent sich dieser [Permission Kalkulator][2]

## umask
Die umask definiert wie die Permission eines neu erstellten Files oder Verzeichnis gesetzt werden.
Sie wird Systemweit in `/etc/login.defs` gesetzt und kann auf User Basis, zum Beispiel in `.bashrc` angepasst werden

Die Octal Werte haben folgende Bedeutung:

|Wert|Permission|
|:--:|--|
|0|read, write and execute|
|1|read and write|
|2| read and execute|
|3|read only|
|4|write and execute|
|5|write only|
|6|execute only|
|7|no permissions|

Eine **umask** von **022** (was meistens Standard ist) entspricht folgenden Permisson

|Wert|Gültig für|Permission|
|:--:|--|--|
|0|Owner|read, write and execute|
|2|Group|read and execute|
|2|Others|read and execute|

Achtung: Die **umask** geht immer von der **Basepermission** aus.

* Standartpermission für Files ist 666, entspricht rw-rw-rw-
* Standartpermission für Verzeichnise ist 777, entspricht rwxrwxrwx

Die effektive Permission  kann anhand der **umask** folgendermassen berechnet werden.

Angenommen wir haben eine **umask** von 022:

Die Formel lautet: `Basepermission - umask`

FilePermission: 666 - 022 = 644 (rw-r-r)
Verzeichnispermission: 777- 022 = 755 (rwxr-xr-x)

Auf gehärteten Systemen wird meistens eine *umask* von 027 verwendet


## wichtige Befehle
|Befehl | Bedeutung|
|:--:|--|
|chmod|Berechtigungen ändern|
|chown|Ownership ändern|
|umask|Standard File Berechtigung; meist 022 was 644 entspricht|


## wichtige Files und Verzeichnisse
|File/Dir | Bedeutung|
|:--:|--|
|/etc/passwd/|lokale User Definition|
|/etc/group|lokale Gruppen Definition|
|/etc/login.defs|Standard User Einstellungen|

## weitere Infos
mehr zu diesem Thema finden sie [hier][1]
