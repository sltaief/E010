[1]: https://www.tuxcademy.org/download/de/adm2/adm2-de-manual.pdf#section.294
[2]: http://toroid.org/sudoers-syntax

# sudo - Super User do

Mit Hilfe von **sudo** können Befehle unter einem anderen User ausgeführt werden. Sudo lässt sich sehr feingranular konfigurieren.

Die Konfiguration von **sudo** wird in der Datei `/etc/sudoers` gespeichert und sollte nur von **root** modifiziert werden.

Zum Modifizieren der sudo Definition sollte immer **visudo** verwendet werden. Theoretisch könnte die Datei */etc/sudoers* mit jedem beliebeigen Texteditor modifiziert werden, der Vorteil beim Editieren mit **visudo** liegt beim Syntaxcheck beim Speichern der Datei.

User eines Systems können mit `sudo -l` ihre vorhandenen sudo Rechte einsehen.

## Aufbau sudo Definition

Der Aufbau einer sudo Definition in /etc/sudoers hat folgenden Syntax

**wer wo = (unter welchem User) (optionen): Befehle**

### Beispiel:

`james ALL = (root) NOPASSWD: ALL`

User *james* darf auf *jedem Host* als user *root* *ohne Passwort* Eingabe *alle Befehle* ausführen.

## Alias

Sehr nützlich ist die Verwendung von Aliases innerhalb der sudo-Definition. Die Definition eines Alias hat folgenden Syntax, wobei der **Alias** Name vorgegeben ist. Der Alias-Name kann frei gewählt werden.

**Alias Alias-Name = Wert1,Wert2,Wert3 ....**

Es stehen unter Anderem folgende Aliases zur Verfügung:

* User_Alias - Liste von Usern für die eine Definition gelten soll
* Runas_Alias - Liste von Accounts unter welchen ein Kommando ausgeführt werden soll
* Host_Alias - Liste von Hosts auf welchen ein Kommando ausgeführt werden kann
* Cmnd_Alias - Liste von Kommandos

## Beispiel einer SUDO Konfiguration

```
# User Alias
User_Alias USR_NORMAL = joe,james
User_Alias USR_ADMIN = joe

# Host Alias
Host_Alias HST_APPL = 192.168.1.156,10.144.0.0,10.71.196.2
Host_Alias HST_DB = 192.168.1.155

# Command Alias
Cmnd_Alias VIEW = /bin/tail, \
                 /usr/bin/head, \
                 /bin/cat, \
                 /usr/bin/ls

Cmnd_Alias REBOOT = /sbin/reboot

###
# Berechtigungen
###

# mit Alias
USR_NORMAL HST_APPL = (root) NOPASSWD: VIEW

# ohne Alias
james jupiter.tbz.ch = (mysql) NOPASSWD: /usr/bin/systemctl stop mysql, /usr/bin/systemctl start mysql

# mit % kann eine Gruppe referenziert werden
%tbz ALL = REBOOT
```

## wichtige Befehle

|Befehl | Bedeutung|
|:--:|--|
|visudo|Editor für /etc/sudoers mit Syntaxcheck|
|sudo| Befehl mit sudo Berechtigungen ausführen|


## weitere Infos
mehr zu diesem Thema finden sie [hier][1] . Einige Beispiele finden sie [hier][2]
