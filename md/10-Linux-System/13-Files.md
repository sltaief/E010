[1]: https://www.tuxcademy.org/download/de/lxk1/lxk1-de-manual.pdf#chapter.107
# Files

Unter Linuxsystemen ist alles ein File. Egal ob es ein *Verzeichnis*, ein *symbolische Link*
oder eine *Textdatei* ist, es ist immer ein **File**

## File Typen

Unix kennt verschiedene Filetypen. Der Filetype wird jeweils mit dem esten Charakter bei einem `ls -l` angezeigt.

```
crw-rw----. 1 root disk     21,   1 May 21 19:24 sg1
crw-rw----. 1 root disk     21,   2 May 21 19:24 sg2
drwxrwxrwt. 2 root root          40 May 21 19:24 shm
crw-------. 1 root root     10, 231 May 21 19:24 snapshot
drwxr-xr-x. 3 root root         180 May 21 19:24 snd
brw-rw----. 1 root cdrom    11,   0 May 21 19:24 sr0
lrwxrwxrwx. 1 root root          15 May 21 19:24 stderr -> /proc/self/fd/2
lrwxrwxrwx. 1 root root          15 May 21 19:24 stdin -> /proc/self/fd/0
lrwxrwxrwx. 1 root root          15 May 21 19:24 stdout -> /proc/self/fd/1
crw-rw-rw-. 1 root tty       5,   0 May 21 19:24 tty
crw--w----. 1 root tty       4,   0 May 21 19:24 tty0
```

|Character|Type|Beschreibung|
|:--:|--|--|
|-|reguläres File| Text Datei, Binary Datei usw..|
|d|Directory|Verzeichnis|
|l|symoblic Link|symbolischer Link auf eine andere Datei|
|b|Block File| Hardware Files, Partitions usw.. meistens unter /dev zu finden|
|c|Character Device|serial stream, typisch für Terminal |
|p|pipe|FIFO|
|s|socket|Applikatorischer Informations Kommunikation|

## mit Files arbeiten

### ls - Files listen

`ls` ist ein sehr einfacher Befehl und dient zum Auflisten von Files und Verzeichnisen.

### touch - leeres File erstellen

`touch <file>`

### cp - Kopieren
Einfaches Kopieren

`cp <file1> <file2>`

Kopieren mit absoluten Pfaden

`cp /var/<file1> /opt/<file2>`

Rekursiv Kopieren, kopiert alles - inkl. Unterverzeichnisen nach /tmp

`cp -R * /tmp/`

### mv - Moven

**Achtung:** mv kennt kein rekursiv, es werden *IMMER* alle Unterverzeichnise mitverschoben

Verschiebt *file1* nach *file2*

 `mv <file1> <file2>`
Verschiebt *dir1* nach */tmp*

`mv <dir1> /tmp/`

### ln - Symlink (Verknüpfung) erstellen

```
$ ln -s realfile linkfile
$ ls -l
lrwxrwxrwx. 1 root root 8 May 23 15:49 linkfile -> realfile
-rw-r--r--. 1 root root 0 May 23 15:49 realfile
```

### Files finden

Unix kennt das Kommando `find` um Files zu finden. Das Kommando ist sehr mächtig, es sind
hier lediglich ein paar Beispiele gezeigt.


Datei *messages* im Verzeichnis /var suchen
```
# find /var -name messages
/var/log/messages
```

Dateien im aktuellen Verzeichnis und allen unterliegenden Verzeichnissen die älter als 3 Tage sind finden

`find . -ctime +3`

Dateien im aktuellen Verzeichnis und allen unterliegenden Verzeichnissen die älter als 3 Tage sind finden
Gefunden Files löschen

`find . -ctime +3 -exec rm {} \;`

Dateien in /opt und darunter suchen, welche User *james* gehören

`find /opt -user james`

Mit einem **!** wird das Kriterium negiert
Dateien in /opt und darunter suchen, welche **nicht** User *james* gehören

`find /opt ! -user james`



## wichtige Befehle
|Befehl | Bedeutung|
|:--:|--|
|ls|Listed Files|
|cp|Kopiert Files/Directory|
|mv|Verschieb Files/Directory|
|ln|Symbolischer Link erstellen|
|find|Findet Files nach bestimmten Kriterien|
|file|Zeigt Filetype an (text/binary usw..)|

## weitere Infos
mehr zu diesem Thema finden sie [hier][1]
