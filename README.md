[1]: https://www.tuxcademy.org/download/de/lxes/lxes-de-manual.pdf
[7]: https://www.tuxcademy.org/

# E010 - Linux Essentials Exam 010

### Topics

* [Topic 1: The Linux Community and a Career in Open Source](#topic-1-the-linux-community-and-a-career-in-open-source)
* [Topic 2: Finding Your Way on a Linux System](#topic-2-finding-your-way-on-a-linux-system)
* [Topic 3: The Power of the Command Line](#topic-3-the-power-of-the-command-line)
* [Topic 4: The Linux Operating System](#topic-4-the-linux-operating-system)
* [Topic 5: Security and File Permissions](#topic-5-security-and-file-permissions)

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
* [Linux Essentials][1] von [tuxcademy][7] - Kapitel 6
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

### 3.2 Searching and Extracting Data from Files
*** 

> [⇧ **Nach oben**](#topics)

### 3.3 Turning Commands into a Script
*** 

> [⇧ **Nach oben**](#topics)



## Topic 4: The Linux Operating System

### 4.1 Choosing an Operating System
*** 

> [⇧ **Nach oben**](#topics)

### 4.2 Understanding Computer Hardware
*** 

> [⇧ **Nach oben**](#topics)

### 4.3 Where Data is Stored 
*** 

> [⇧ **Nach oben**](#topics)

### 4.4 Your Computer on the Network
*** 

> [⇧ **Nach oben**](#topics)

## Topic 5: Security and File Permissions

### 5.1 Basic Security and Identifying User Types
*** 

> [⇧ **Nach oben**](#topics)

### 5.2 Creating Users and Groups
*** 

> [⇧ **Nach oben**](#topics)

### 5.3 Managing File Permissions and Ownership
*** 

> [⇧ **Nach oben**](#topics)

### 5.4 Special Directories and Files
*** 

> [⇧ **Nach oben**](#topics)