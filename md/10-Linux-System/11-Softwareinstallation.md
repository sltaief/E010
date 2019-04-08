[3]: https://www.cyberciti.biz/howto/question/linux/linux-rpm-cheat-sheet.php
# Software installieren und managen

Auf jedem System wird irgendwann Software installiert, aktualisiert oder deinstalliert werden müssen. Früher wurde das auf Unix Systemen oft mittels tar-Files, welche vergleichbar mit einem zip-File sind, gemacht - also die Software wurde einfach hin kopiert. Updates waren so sehr schwierig und Inkonsistenzen innerhalb der Systeme waren nicht selten.

Heute verwendet man anstelle von tar-Files Software Pakete. Im Falle von Redhat, Fedora,SuSE und auch CentOS sind das **rpm-Packete**. Zum Verwalten der Softwarepakete wird das Tool **yum** verwendet. Yum bedient sich sogenannten Repositories, auf welchen **rpm** Pakete abgelegt sind. Repositories können lokale Ablagen sein, oft sind es jedoch Ablagen welche im Internet sind, aber auch ein lokales ISO Image kann als Repository definiert werden.

## yum - Softwaremanager
**yum** wird zum Installieren und Deinstallieren oder ganz allgemein zum Verwalten der Software verwendet.
Die Pakete selber sind im RPM Format abgelegt.

## rpm - Redhat Paket Manager
**rpm** ist das Format der Software Packages. Sie sind vergleichbar mit den bei Windows bekannten MSI-Dateien.

Obschon rpm-Pakete direkt mittels rpm Kommandos (rpm -i <packet>) installiert werden könnten, sollte immer **yum** dazu verwendet werden. Yum macht Abhängigkeitsprüfungen und sorgt so damit, dass es keine Inkonsistenzen unter den Installierten Packages gibt.

Trotzdem sind rpm Kommandos sehr nützlich. So kann beispielsweise mit `rpm -qa` eine Liste aller installierter Pakete auf einem System ausgegeben werden.

Eine Übersicht über die wichtigsten **rpm Kommandos** finden sie [hier][3]


## lokales yum Repository anlegen

### Vorbereitung in der VirtualBox

Vorgängig muss das **Installation ISO File**  in der VirtualBox unter Massenspeicher/CDROM eingelegt werden.

*WICHTIG:* im Ausgeschalteten Zustand der VM, die Boot Order so anpassen, dass nicht ab CDROM gestartet wird.

### Vorbereitung im Linux Systeme


Zuerst muss das Verzeichnis `/cdrom` erstellt und anschliessend das Image in das Verzeichnis gemounted werden.

`# mkdir /cdrom`

`# mount /dev/cdrom /cdrom`

Mit `ls -l /cdrom` kann geprüft werden, ob der Inhalt im Verzeichnis vorhanden ist. Ist das der Fall, ist die CDROM *gemounted*.


Die Repositories werden im Verzeichnis `/etc/yum.repos.d` definiert.
Da wir ohne Internetzugriff arbeiten, verwenden wir ein lokals Repository.

Zuerst werden alle bereits vorhandenen Repository folgendermassen deaktiviert

`# cd /etc/yum.repos.d`

`# for i in $(ls *.repo); do mv $i $i.orig; done`

Das Deaktivieren ist nötig, damit das System nicht in den (nicht erreichbaren) Internet-Repository suchen geht.

Anschliessend das lokales Repository folgendermassen definieren

```
# cd /etc/yum.repos.d

cat << EOF > local.repo
[localRepo]
name=LocalRepository
baseurl=file:///cdrom
enabled=1
gpgcheck=0
EOF
```

### Kontrolle des lokalen Repository

Bestehende Repsoitory Datenbank löschen. Der Befehl löscht nur den Index, es werden keine
Dateien gelöscht.

`# yum clean all`

Aktuelle Repository anzeigen

`# yum repolist`

### mit yum arbeiten

Pakete suchen

`# yum search {such Pattern}`

Suchen welches Packet eine bestimmte Datei enthält

`# yum provides {such Pattern}`

Software Packet installieren

`# yum install <pkg>`

Software Packet entfernen

`# yum remove <pkg>`

Zeigt den Verlauf der Software Installationen an

`# yum history`

#### Beispiel einer Software Installation, Kontrolle und Deinstallation

```

[root@bem bin]# yum install telnet
Loaded plugins: fastestmirror
Loading mirror speeds from cached hostfile
Resolving Dependencies
--> Running transaction check
---> Package telnet.x86_64 1:0.17-64.el7 will be installed
--> Finished Dependency Resolution

Dependencies Resolved

====================================================================================================
 Package             Arch                Version                       Repository              Size
====================================================================================================
Installing:
 telnet              x86_64              1:0.17-64.el7                 localRepo               64 k

Transaction Summary
====================================================================================================
Install  1 Package

Total download size: 64 k
Installed size: 113 k
Is this ok [y/d/N]: y
Downloading packages:
Running transaction check
Running transaction test
Transaction test succeeded
Running transaction
  Installing : 1:telnet-0.17-64.el7.x86_64                                                      1/1
  Verifying  : 1:telnet-0.17-64.el7.x86_64                                                      1/1

Installed:
  telnet.x86_64 1:0.17-64.el7

Complete!
[root@bem bin]# yum history
Loaded plugins: fastestmirror
ID     | Login user               | Date and time    | Action(s)      | Altered
-------------------------------------------------------------------------------
     2 | root <root>              | 2018-05-31 19:50 | Install        |    1
     1 | System <unset>           | 2018-05-11 13:29 | Install        |  301
history list
[root@bem bin]# yum history info 2
Loaded plugins: fastestmirror
Transaction ID : 2
Begin time     : Thu May 31 19:50:11 2018
Begin rpmdb    : 301:62f785fbab91b8201c05eec845b88bdf864d4b82
End time       :                           (0 seconds)
End rpmdb      : 302:767ddbfa66dc0b27f10cda5e09cb5b9421224dd9
User           : root <root>
Return-Code    : Success
Command Line   : install telnet
Transaction performed with:
    Installed     rpm-4.11.3-32.el7.x86_64                      @anaconda
    Installed     yum-3.4.3-158.el7.centos.noarch               @anaconda
    Installed     yum-plugin-fastestmirror-1.1.31-45.el7.noarch @anaconda
Packages Altered:
    Install telnet-1:0.17-64.el7.x86_64 @localRepo
history info

## Software entfernen

[root@bem bin]# yum remove telnet-1:0.17-64.el7.x86_64
Loaded plugins: fastestmirror
Resolving Dependencies
--> Running transaction check
---> Package telnet.x86_64 1:0.17-64.el7 will be erased
--> Finished Dependency Resolution

Dependencies Resolved

====================================================================================================
 Package             Arch                Version                      Repository               Size
====================================================================================================
Removing:
 telnet              x86_64              1:0.17-64.el7                @localRepo              113 k

Transaction Summary
====================================================================================================
Remove  1 Package

Installed size: 113 k
Is this ok [y/N]: y
Downloading packages:
Running transaction check
Running transaction test
Transaction test succeeded
Running transaction
  Erasing    : 1:telnet-0.17-64.el7.x86_64                                                      1/1
  Verifying  : 1:telnet-0.17-64.el7.x86_64                                                      1/1

Removed:
  telnet.x86_64 1:0.17-64.el7

Complete!
[root@bem bin]#

```

Eine gute Übersicht wie **yum** verwendet wird ist in diesem [One-Pager][1] enthalten

## wichtige Befehle
|Befehl|Bedeutung|
|:--:|--|
|yum|Installer , Paketmanager|
|rpm|Paketmanager|
|mount|Dateisystem einhängen|

## wichtige Files und Verzeichnisse
|File/Dir | Bedeutung|
|:--:|--|
|/etc/yum.repos.d/|Definition der yum Repositories|
