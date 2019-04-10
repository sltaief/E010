[1]: https://www.tuxcademy.org/download/de/lxes/lxes-de-manual.pdf
[7]: https://www.tuxcademy.org/

# ![](https://www.lpice.eu/fileadmin/_processed_/csm_LinuxEssentials-01_0ab118aa19.jpg) E010 - Linux Essentials Exam 010

### Topics

* [Topic 1: The Linux Community and a Career in Open Source](#topic-1-the-linux-community-and-a-career-in-open-source)
* [Topic 2: Finding Your Way on a Linux System](#topic-2-finding-your-way-on-a-linux-system)
* [Topic 3: The Power of the Command Line](#topic-3-the-power-of-the-command-line)
* [Topic 4: The Linux Operating System](#topic-4-the-linux-operating-system)
* [Topic 5: Security and File Permissions](#topic-5-security-and-file-permissions)
* [Bonusmaterial](#bonusmaterial)

## Topic 1: The Linux Community and a Career in Open Source

### 1.1 Linux Evolution and Popular Operating Systems
*** 

> [⇧ **Nach oben**](#topics)

**Weight**: 2

**Description**: Knowledge of Linux development and major distributions

Key Knowledge Areas:
* Distributions
* Embedded Systems
* Linux in the Cloud

The following is a partial list of the used files, terms and utilities:
* Debian, Ubuntu (LTS)
* CentOS, openSUSE, Red Hat, SUSE
* Linux Mint, Scientific Linux
* Raspberry Pi, Raspbian
* Android

**Unterlagen**: [Linux Essentials][1] von [tuxcademy][7] - Kapitel 1

**Linux Distributionen**

* [Red Hat](http://www.redhat.com/) wurde 1993 unter dem Namen »ACC Corporation« als Vertriebsfirma für Linux- und Unix-Zubehör gegründet.

 
* Die Firma [SUSE](https://www.suse.com/de-de/) wurde 1992 unter dem Namen »Gesellschaft für Software- und System-Entwicklung« als Unix-Beratungshaus gegründet.


* Im Gegensatz zu den beiden großen Linux-Distributionsfirmen Red Hat und Novell/SUSE ist das [Debian-Projekt](http://www.debian.org/) ein Zusammenschluss von Freiwilligen.


* Der wahrscheinlich populärste Debian-Ableger ist [Ubuntu](http://www.ubuntu.com/), das von der britischen Firma Canonical Ltd. des südafrikanischen Unternehmers Mark Shuttleworth angeboten wird.


### 1.2 Major Open Source Applications
*** 

> [⇧ **Nach oben**](#topics)

**Weight**: 2

**Description**: Awareness of major applications as well as their uses and development.

Key Knowledge Areas:
* Desktop applications - OpenOffice.org, LibreOffice, Thunderbird, Firefox, GIMP
* Server applications - Nextcloud, ownCloud, Apache HTTPD, NGINX, MariaDB, MySQL, NFS, Samba
* Development languages - C, Java, JavaScript, Perl, shell, Python, PHP
* Package management tools and repositories - dpkg, apt-get (apt), rpm, yum

**Unterlagen**:

* [Software installieren und managen](md/10-Linux-System/11-Softwareinstallation.md)
 
**Hinweis**: Nicht in den Unterlagen erwähnte Produkte googlen.

### 1.3 Open Source Software and Licensing
*** 

> [⇧ **Nach oben**](#topics)

**Weight**: 1

**Description**: Open communities and licensing Open Source Software for business.

Key Knowledge Areas:
* Open source philosophy
* Open source licensing
* Free Software Foundation (FSF), Open Source Initiative (OSI)

The following is a partial list of the used files, terms and utilities:
* Copyleft, Permissive
* GPL, BSD, Creative Commons
* Free Software, Open Source Software, FOSS, FLOSS
* Open source business models

**Unterlagen**: [Linux Essentials][1] von [tuxcademy][7] - Kapitel 2

**Urheberrecht**

Urheberrecht bedeutet dass dem Urheber eines Werks, also dem Autor eines Buchs, Maler eines Bildes, … das Recht zuerkannt wird, als Einziger darüber zu verfügen, was mit dem Werk passiert.

Wie wird eine Software zur »freien« oder »Open-Source«-Software? 
* Urheber kann Rechte, in Form einer Lizenz, an andere weitergegeben

**Lizenzen**

Die Lizenzen für freie und Open-Source-Software dienen dazu, dem Erwerber der Software Dinge zu erlauben, die er laut Urheberrechtsgesetz eigentlich nicht haben dürfte.

* **Copyleft-Lizenz**: GPL (u.a. eingesetzt für den Linux Kernel) soll sicherstellen, dass Software, die einmal unter der GPL steht, auch weiter unter der GPL bleibt.
* **Ohne Copyleft**: Apache, BSD, MIT. Software kann in seine eigenen Programme integriert und diese Programme in ausführbarer Form weitergeben werden.

siehe: [https://opensource.org/licenses](https://opensource.org/licenses)

### 1.4 ICT Skills and Working in Linux
*** 

> [⇧ **Nach oben**](#topics)

**Weight**: 2

**Description**: Basic Information and Communication Technology (ICT) skills and working in Linux.

Key Knowledge Areas:
* Desktop skills
* Getting to the command line
* Industry uses of Linux, cloud computing and virtualization

The following is a partial list of the used files, terms and utilities:
* Using a browser, privacy concerns, configuration options, searching the web and saving content
* Terminal and console
* Password issues
* Privacy issues and tools
* Use of common open source applications in presentations and projects

**Unterlagen**: [Linux Essentials][1] von [tuxcademy][7] - Kapitel 3

## Topic 2: Finding Your Way on a Linux System

### 2.1 Command Line Basics
*** 

> [⇧ **Nach oben**](#topics)

**Weight**: 3

**Description**: Basics of using the Linux command line.

Key Knowledge Areas:
* Basic shell
* Command line syntax
* Variables
* Quoting

The following is a partial list of the used files, terms and utilities:
* Bash
* echo
* history
* PATH environment variable
* export
* type

**Unterlagen**: [Linux Essentials][1] von [tuxcademy][7] - Kapitel 4

### 2.2 Using the Command Line to Get Help
*** 

> [⇧ **Nach oben**](#topics)

**Weight**: 2

**Description**: Running help commands and navigation of the various help systems.

Key Knowledge Areas:
* Man pages
* Info pages

The following is a partial list of the used files, terms and utilities:
* man
* info
* /usr/share/doc/
* locate

**Unterlagen**: [Linux Essentials][1] von [tuxcademy][7] - Kapitel 5

### 2.3 Using Directories and Listing Files
*** 

> [⇧ **Nach oben**](#topics)

**Weight**: 2

**Description**: Navigation of home and system directories and listing files in various locations.

Key Knowledge Areas:
* Files, directories
* Hidden files and directories
* Home directories
* Absolute and relative paths

The following is a partial list of the used files, terms and utilities:
* Common options for ls
* Recursive listings
* cd
* . and ..
* home and ~

**Unterlagen**: 
* [Linux Essentials][1] von [tuxcademy][7] - Kapitel 6 und Kapitel 10
* [Filesystem](md/10-Linux-System/12-Filesystem.md)

### 2.4 Creating, Moving and Deleting Files
*** 

> [⇧ **Nach oben**](#topics)

**Weight**: 2

**Description**: Create, move and delete files and directories under the home directory.

Key Knowledge Areas:
* Files and directories
* Case sensitivity
* Simple globbing

The following is a partial list of the used files, terms and utilities:
* mv, cp, rm, touch
* mkdir, rmdir

**Unterlagen**: 
* [Linux Essentials][1] von [tuxcademy][7] - Kapitel 6 (letzte zwei Kapitel)
* [Files](md/10-Linux-System/13-Files.md)

## Topic 3: The Power of the Command Line

### 3.1 Archiving Files on the Command Line
*** 

> [⇧ **Nach oben**](#topics)

**Weight**:  2

**Description**: Archiving files in the user home directory.

Key Knowledge Areas:
* Files, directories
* Archives, compression

The following is a partial list of the used files, terms and utilities:
* tar
* Common tar options
* gzip, bzip2, xz
* zip, unzip

**Unterlagen**: 
* [Linux Essentials][1] von [tuxcademy][7] - Kapitel 11

### 3.2 Searching and Extracting Data from Files
*** 

> [⇧ **Nach oben**](#topics)

**Weight**: 3

**Description**: Search and extract data from files in the home directory.

Key Knowledge Areas:
* Command line pipes
* I/O redirection
* Basic Regular Expressions using ., [ ], *, and ?

The following is a partial list of the used files, terms and utilities:
* grep
* less
* cat, head, tail
* sort
* cut
* wc

**Unterlagen**: 
* [Linux Essentials][1] von [tuxcademy][7] - Kapitel 8
* [Standard-Datenströme](md/10-Linux-System/16-Standard-Datenstroeme.md)
* [File Manipulationen](md/10-Linux-System/30-Filemanipulationen.md)

**cat** (Kapitel 8.3.1)

cat ist ursprünglich zum Zusammenfügen von Dateien gedacht (von concatenate = verketten, verknüpfen).

	cat >main.js <<%EOF%
		console.log(‘Hallo Welt’);
	%EOF%
	ssh <server> tar czf - /etc | cat - >sicherung.tgz 

**head, tail, less** (Kapitel 8.3.2)

head + tail - Anfang und Ende von Dateien

	head /proc/cpuinfo
	tail /var/log/apache2/error.log
	tail -f /var/log/apache2/access.log
	
less oder more - Zeigt Texte (etwa Handbuchseiten) seitenweise an

	less /proc/cpuinfo

**wc, sort, uniq** (Kapitel 8.3.1)

**wc** – zählt die Anzahl Wörter, Zeilen

	wc /proc/cpuinfo
	ls -l | wc –l

**sort** - Sortiert die Zeilen seiner Eingabe

	ls | sort

**uniq** - Entfernt doppelte Einträge

	cat <meineDaten> | sort | uniq
	
**cut** (Kapitel 8.4.2)

**cut** - Extrahiert Felder oder Spalten aus seiner Eingabe

	cut -d: -f1 /etc/passwd | sort
	cut –c1-3 /etc/passwd | sort | uniq | wc -l
	
siehe auch: [https://wiki.ubuntuusers.de/cut/](https://wiki.ubuntuusers.de/cut/)

**Reguläre Ausdrücke** (Kapitel 7)

Ein regulärer Ausdruck (englisch regular expression) ist eine Zeichenkette, die der Beschreibung von Mengen von Zeichenketten mit Hilfe bestimmter syntaktischer Regeln dient.

	^ - Beginn Zeile, $ - Ende Zeile
	[] – Ausdruck beinhaltet Zeichen, z.B. [A-Z]
	
**Wildcards**: * - beliebige Wiederholungen, . – ein beliebiges Zeichen.

**grep** (Kapitel 7.3)

**grep, fgrep, egrep** - Sucht in Dateien nach Zeilen mit bestimmtem Inhalt

	grep ubuntu /etc/passwd 
	grep –v ubuntu /etc/passwd 
	grep ^[a-z] /etc/passwd
	
siehe auch: [https://wiki.ubuntuusers.de/grep/](https://wiki.ubuntuusers.de/grep/)

**sed** 

**sed** (von stream editor) ist ein nicht-interaktiver Texteditor für die Verwendung auf der Kommandozeile oder in Skripten.

	sudo sed -i -e"s/^bind-address\s*=\s*127.0.0.1/bind-address = 0.0.0.0/" /etc/mysql/mysql.conf.d/mysqld.cnf
	
siehe auch: [https://wiki.ubuntuusers.de/sed/](https://wiki.ubuntuusers.de/sed/)

**awk**

**awk** - ist eine einfache Programmiersprache für Textverarbeitungszwecke (im weitesten Sinne).

	awk ‘BEGIN { print "Die IP Adresse von localhost ist: " }
	$2 == "localhost" { print $1 }
	END   { print "Das war die IP Adresse von localhost."}
	 ' /etc/hosts 
	awk '$2 == "localhost" { printf("IP: %s\n", $1 )}' /etc/hosts

siehe auch: [https://wiki.ubuntuusers.de/awk/](https://wiki.ubuntuusers.de/awk/)	

### 3.3 Turning Commands into a Script
*** 

> [⇧ **Nach oben**](#topics)

**Weight**: 4

**Description**: Turning repetitive commands into simple scripts.

Key Knowledge Areas:
* Basic shell scripting
* Awareness of common text editors (vi and nano)

The following is a partial list of the used files, terms and utilities:
* #! (shebang)
* /bin/bash
* Variables
* Arguments
* for loops
* echo
* Exit status

**Unterlagen**: 
* [Linux Essentials][1] von [tuxcademy][7] - Kapitel 9
* [Prozesse](md/10-Linux-System/18-Prozesse.md)
* [sudo](md/10-Linux-System/31-sudo.md)
* [vi Text Editor](md/10-Linux-System/32-VI_Editor.md)

**Linux Grundsatz** (#! (shebang))

* Es werden beliebige Scriptsprachen unterstützt
* Der 1. Eintrag in einer Datei bestimmt die Script-Umgebung

Beispiele:

```Shell
	#!/bin/bash – Bash Script
	#!/usr/bin/node – Node JavaScript
	#!/usr/bin/perl - Perl
```

**Linux Dateirechte**

* **x - Ausführen (execute)**: Erlaubt das Ausführen einer Datei, wie das Starten eines Programms. Bei einem Verzeichnis ermöglicht dieses Recht, in diesen Ordner zu wechseln und weitere Attribute zu den enthaltenen Dateien abzurufen (sofern man die Dateinamen kennt ist dies unabhängig vom Leserecht auf diesen Ordner). Statt x kann auch ein Sonderrecht angeführt sein.

* **s -Set-UID-Recht (SUID-Bit)**: Das Set-UID-Recht („Set User ID“ bzw. „Setze Benutzerkennung“) sorgt bei einer Datei mit Ausführungsrechten dafür, dass dieses Programm immer mit den Rechten des Dateibesitzers läuft. Bei Ordnern ist dieses Bit ohne Bedeutung.

Befehle: `chmod +x <Datei>; chmod u+s <Datei>`

**PATH + Verzeichnisse**

* PATH Variable legt fest wo ausführbare Programme und Dateien gesucht werden.

Beispiel:

	export PATH=$HOME/bin:$PATH
	
Wichtige Verzeichnisse

	$HOME/bin oder ~/bin – eigene Programme/Scripts
	/usr/local/bin – eigene für alle User
	/bin, /usr/bin – Normale Programme 
	/sbin, /usr/sbin – System Programme 

**Argumente + Rückgabewert**

Übergabe

	$1 - $x – Argumente
	$0 – Name Script (z.B. gleiches Script wo anders reagiert, je nach Namen)
	$# - Anzahl Argumente, $* alle Argumente
	
Rückgabewerte

	$? – Rückgabewert, z.B. exit 1, exit 0, exit -1

## Topic 4: The Linux Operating System

### 4.1 Choosing an Operating System
*** 

> [⇧ **Nach oben**](#topics)

**Weight**: 1

**Description**: Knowledge of major operating systems and Linux distributions.

Key Knowledge Areas:
* Differences between Windows, OS X and Linux
* Distribution life cycle management

The following is a partial list of the used files, terms and utilities:
* GUI versus command line, desktop configuration
* Maintenance cycles, beta and stable

**Unterlagen**: [Linux Essentials][1] von [tuxcademy][7] - Kapitel 1

### 4.2 Understanding Computer Hardware
*** 

> [⇧ **Nach oben**](#topics)

**Weight**: 2

**Description**: Familiarity with the components that go into building desktop and server computers.

Key Knowledge Areas:
* Hardware

The following is a partial list of the used files, terms and utilities:
* Motherboards, processors, power supplies, optical drives, peripherals
* Hard drives, solid state disks and partitions, /dev/sd*
* Drivers

**Unterlagen**: [Linux Essentials][1] von [tuxcademy][7] - Kapitel 1

### 4.3 Where Data is Stored 
*** 

> [⇧ **Nach oben**](#topics)

**Weight**: 3

**Description**: Where various types of information are stored on a Linux system.

Key Knowledge Areas:
* Programs and configuration
* Processes
* Memory addresses
* System messaging
* Logging

The following is a partial list of the used files, terms and utilities:
* ps, top, free
* syslog, dmesg
* /etc/, /var/log/
* /boot/, /proc/, /dev/, /sys/

**Unterlagen**: 
* [Boot Prozess](md/10-Linux-System/23-Boot-Prozess.md)
* [System V](md/10-Linux-System/24-System-V.md)

### 4.4 Your Computer on the Network
*** 

> [⇧ **Nach oben**](#topics)

**Weight**: 2

**Description**: Querying vital networking configuration and determining the basic requirements for a computer on a Local Area Network (LAN).

Key Knowledge Areas:
* Internet, network, routers
* Querying DNS client configuration
* Querying network configuration

The following is a partial list of the used files, terms and utilities:
* route, ip route show
* ifconfig, ip addr show
* netstat, ss
* /etc/resolv.conf, /etc/hosts
* IPv4, IPv6
* ping
* host

**Unterlagen**: 
* [Linux Essentials][1] von [tuxcademy][7] - Kapitel 15
* [Standard Datenströme](md/10-Linux-System/16-Standard-Datenstroeme.md)
* [File Manipulationen](md/10-Linux-System/30-Filemanipulationen.md)

## Topic 5: Security and File Permissions

### 5.1 Basic Security and Identifying User Types
*** 

> [⇧ **Nach oben**](#topics)

**Weight**: 2

**Description**: Various types of users on a Linux system.

Key Knowledge Areas:
* Root and standard users
* System users

The following is a partial list of the used files, terms and utilities:
* /etc/passwd, /etc/shadow, /etc/group
* id, last, who, w
* sudo, su

**Unterlagen**: 
* [Linux Essentials][1] von [tuxcademy][7] - Kapitel 13
* [sudo](md/10-Linux-System/31-sudo.md)

### 5.2 Creating Users and Groups
*** 

> [⇧ **Nach oben**](#topics)

**Weight**: 2

**Description**: Creating users and groups on a Linux system.

Key Knowledge Areas:
* User and group commands
* User IDs

The following is a partial list of the used files, terms and utilities:
* /etc/passwd, /etc/shadow, /etc/group, /etc/skel/
* useradd, groupadd
* passwd

**Unterlagen**: 
* [Linux Essentials][1] von [tuxcademy][7] - Kapitel 13
* [User and Groups](md/10-Linux-System/14-User_Groups.md)
* [Permissions](md/10-Linux-System/15-Permissions.md)

### 5.3 Managing File Permissions and Ownership
*** 

> [⇧ **Nach oben**](#topics)

**Weight**: 2

**Description**: Understanding and manipulating file permissions and ownership settings.

Key Knowledge Areas:
* File and directory permissions and ownership

The following is a partial list of the used files, terms and utilities:
* ls -l, ls -a
* chmod, chown

**Unterlagen**: 
* [Linux Essentials][1] von [tuxcademy][7] - Kapitel 14
* [Permissions](md/10-Linux-System/15-Permissions.md)

### 5.4 Special Directories and Files
*** 

> [⇧ **Nach oben**](#topics)

**Weight**: 1

**Description**: Special directories and files on a Linux system including special permissions.

Key Knowledge Areas:
* Using temporary files and directories
* Symbolic links

The following is a partial list of the used files, terms and utilities:
* /tmp/, /var/tmp/ and Sticky Bit
* ls -d
* ln -s

**Unterlagen**: 
* [Linux Essentials][1] von [tuxcademy][7] - Kapitel 14
* [Permissions](md/10-Linux-System/15-Permissions.md)

## Bonusmaterial

> [⇧ **Nach oben**](#topics)

* [Troubleshooting](md/10-Linux-System/35-Troubleshooting.md)
* [Scheduler](md/10-Linux-System/17-Scheduler.md)
* [Disk LVM](md/10-Linux-System/21-Disk-LVM.md)
* [Commands](md/10-Linux-System/90-Commands.md)
* [Ergänzende Unterlagen aus Modul M300](https://github.com/mc-b/M300/tree/master/80-Ergaenzungen)


