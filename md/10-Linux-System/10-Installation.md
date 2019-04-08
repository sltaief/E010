[1]: https://www.tuxcademy.org/media/basic/
[2]: https://www.tuxcademy.org/download/de/lxk1/lxk1-de-manual.pdf
[7]: https://www.tuxcademy.org/
[8]: https://access.redhat.com/node/1284753/40/0
[9]: https://www.cyberciti.biz/howto/question/linux/linux-rpm-cheat-sheet.php
[10]: https://www.tuxcademy.org/download/de/lxk1/lxk1-de-manual.pdf#appendix.1014
# W901 – Basis-Installation

## Unterrichts Dokumentation
Sie finden zu allen Themen mehr Informationen in der frei verfügbare [Dokumentation][1] von [tuxcademy][7]  


## Software

| Verwendung | Produkt | Version | URL |
|--|--|:--:|--|
| Virtualisierung | VirtualBox|5.2.8 | https://www.virtualbox.org/wiki/Downloads |
| Linux Distribution | CentOS 64Bit | 7.5 | http://mirror.switch.ch/ftp/mirror/centos/7/isos/x86_64/CentOS-7-x86_64-DVD-1804.iso| |
|Windows SSH Client| putty|0.7| https://putty.org/ |
|Grafischer Windows SFTP Client | Bitvise SSH Client| 7.42 |https://www.bitvise.com/ssh-client-download |

## VM Setup für den Unterricht

|VirtualBox||
|--|--|
|VM Name| CentOS-base|
|Netzwerk|Netzwerkbrücke (Bridge)|
|Massenspeicher – 2 Disk|Controller:SATA ; Disk0, Disk1 - je 8GB, dynamisch|

|CentOS||
|--|--|
|Sprache|English (United States)|
|Localisation|Date&Time: Europe/Zurich|
|Keymap|Keyboard: (muss Hostsystem entsprechen); Swiss German (German (Switzerland))|
|Installation Source|Local media|
|Software Selection|Minimal Install|
|Installation Destination| Disk0 (sda)|
|Network & Hostname|enp0s3 , Schalter auf on setzen! ; IPv6 Settings - ignore ;Hostname belassen, wird später gesetzt|
|Passwort root Account| w901|

Belassen sie nach der Installation alle Installationsquellen während der Dauer des Moduls auf ihrem Laptop.


## weitere Infos
mehr zu diesem Thema finden sie Hier
+ [yum-Cheatsheet][8]
+ [rpm-Cheatsheet][9]
+ [LPC1-Zertifizierung][10]
