[1]: https://www.tuxcademy.org/download/de/lxk1/lxk1-de-manual.pdf#chapter.324

# User und Gruppen

Jedem User und jeder Gruppe wird eine eindeutige **ID** zugewiesen. Dabei muss zwischen **normalen**
User und Gruppen und **system** User und Gruppen unterschiednen werden.

Normale User und Gruppen sind eigentliche Benutzer des Systems, auch sogenannte **Login-User**
System Usser und Gruppen sind wie der Name schon verrät, fürs System reserviert.

Normale User/Gruppen und System User/Gruppen haben unterschiedliche Ranges von ID's. Wird beispielsweise der Befehl `useradd` zum Erstellen eines User ohne Angaben einer User ID (uid) ausgeführt, so wird eine freie (es ist immer die nächst höhere der bereits höchsten vergebenen ID) erteilt.  

Der Range der ID's wird im Konfigurationsfile `/etc/login.defs` definiert. Die aktuellen Werte können
folgendermassen abgefragt werden:

```
# grep [UG]ID /etc/login.defs
UID_MIN                  1000
UID_MAX                 60000
SYS_UID_MIN               201
SYS_UID_MAX               999
GID_MIN                  1000
GID_MAX                 60000
SYS_GID_MIN               201
SYS_GID_MAX               999
```

Der Befehl `id -a` , resp. `id -a <user>` gibt die einem User zugewiesenen Gruppen aus.

## User und Gruppen anlegen

### User anlegen

Zum anlegen eines User wird der Befhel `useradd` verwendet. Es wird zu jedem User
zugleich eine gleichnamige Gruppe erstellt, welchem dem erstellten User als standard Gruppe
zugewiesen wird (primary Group).

Beispiel, User *bem* mit Standardwerten anlegen:
```
[root@localhost skel]# useradd -c "TBZ User" -m -s /bin/bash bem
[root@localhost skel]# id -a bem
uid=1000(bem) gid=1000(bem) groups=1000(bem)
[root@localhost skel]# tail -1 /etc/passwd
bem:x:1000:1000:TBZ User:/home/bem:/bin/bash
```

### User inklusive Home-Verzeichnis löschen
Zum löschen eines User wird der Befhel `userdel` verwendet.

`userdel -r <user>`

### Gruppe anlegen
Zum anlegen einer Gruppe wird der Befhel `groupadd` verwendet.

`groupadd <grp-name>`

### Gruppe löschen
Zum löschen einer Gruppe wird der Befehl `groupdel` verwendet.

`groupdel <grp-name>`

## Begriffe
|Begriff|Bedeutung|
|:--:|--|
|uid|User ID, root hat immer UID 0|
|gid|Group ID, root hat immer GID 0|
|primary Group| die Primäre Gruppe eines Userss|
|secondary Group|zusätzliche Gruppen eines Users|

## wichtige Befehle
|Befehl | Bedeutung|
|:--:|--|
|id|zeigt User ID und Gruppen Mebership|
|useradd|User anlegen|
|userdel|User löschen|
|groupadd|Gruppe anlegen|
|groupdel|Gruppe löschen|

## wichtige Files und Verzeichnisse
|File/Dir | Bedeutung|
|:--:|--|
|/etc/passwd|Definition der lokalen User (aber nicht der Passwörter)|
|/etc/shadow|Verschlüsselte Passwörter der User|
|/etc/group|Definition der Gruppen|
|/etc/login.defs|Standard User Einstellungen|
|/etc/profile|Default Bash Profile Settings|

## weitere Infos
mehr zu diesem Thema finden sie [hier][1]
