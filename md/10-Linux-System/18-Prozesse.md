[1]: https://www.tuxcademy.org/download/de/adm1/adm1-de-manual.pdf#chapter.89
[2]: https://www.selflinux.org/selflinux/index.html
[3]: https://www.selflinux.org/selflinux/html/prozessverwaltung02.html
# Prozesse
Jeder Prozess hat einen *parent* Prozess. Der *root* Prozess ist Prozess *0* und gehört *root*. Alle weiteren Prozesse sind *child* Prozesse von diesem *root Prozess*

Prozesse können im **Foreground** oder **Background** ausgeführt werden. Sie könne mit entsprechenden Signalen beeinflusst werden, beispielsweise mit `kill -9`.

Ebenfalls kann die Priorität eines Prozesses mit `nice` und `renice` beeinflusst werden.

Die Prozessverwaltung ist eine relativ komplexe Sache und es braucht etwas Übung beim Umgang mit ihnen.

[SelfLinux][2] bietet eine gute [Prozess Dokumentation][3]


## Prozesse monitoren

+ ps
+ top
+ pgrep
+ pstree

### Beispiele

#### Prozesse mit `ps` auflisten

Alle Prozesse im *long* Format

```
$ ps -lax
F   UID   PID  PPID PRI  NI    VSZ   RSS WCHAN  STAT TTY        TIME COMMAND
4     0     1     0  20   0 127932  6452 ep_pol Ss   ?          0:03 /usr/lib/systemd/systemd
1     0     2     0  20   0      0     0 kthrea S    ?          0:00 [kthreadd]
1     0     3     2  20   0      0     0 smpboo S    ?          0:00 [ksoftirqd/0]
1     0     5     2   0 -20      0     0 worker S<   ?          0:00 [kworker/0:0H]
1     0     7     2 -100  -      0     0 smpboo S    ?          0:00 [migration/0]
1     0     8     2  20   0      0     0 rcu_gp S    ?          0:00 [rcu_bh]
1     0     9     2  20   0      0     0 ?      R    ?          0:00 [rcu_sched]
1     0    10     2   0 -20      0     0 rescue S<   ?          0:00 [lru-add-drain]
5     0    11     2 -100  -      0     0 smpboo S    ?          0:00 [watchdog/0]
5     0    13     2  20   0      0     0 devtmp S    ?          0:00 [kdevtmpfs]
1     0    14     2   0 -20      0     0 rescue S<   ?          0:00 [netns]
1     0    15     2  20   0      0     0 watchd S    ?          0:00 [khungtaskd]
1     0    16     2   0 -20      0     0 rescue S<   ?          0:00 [writeback]
1     0    17     2   0 -20      0     0 rescue S<   ?          0:00 [kintegrityd]
1     0    18     2   0 -20      0     0 rescue S<   ?          0:00 [bioset]
1     0    19     2   0 -20      0     0 rescue S<   ?          0:00 [kblockd]
1     0    20     2   0 -20      0     0 rescue S<   ?          0:00 [md]
```

Baum-Darstellung der Prozesse mit `ps`

```
$ ps -aef --forest
UID        PID  PPID  C STIME TTY          TIME CMD
root       867     1  0 09:07 ?        00:00:00 /usr/bin/python -Es /usr/sbin/tuned -l -P
root       869     1  0 09:07 ?        00:00:00 /usr/sbin/sshd -D
root      1135   869  0 09:09 ?        00:00:00  \_ sshd: root@pts/0
root      1139  1135  0 09:09 ?        00:00:00  |   \_ /usr/libexec/openssh/sftp-server
root      1140  1135  0 09:09 ?        00:00:00  |   \_ /usr/libexec/openssh/sftp-server
root      1142  1135  0 09:09 pts/0    00:00:00  |   \_ -bash
root      1287  1142 99 09:36 pts/0    00:06:34  |       \_ dd if=/dev/zero of=/dev/null
root      1294  1142  0 09:43 pts/0    00:00:00  |       \_ su - bem
bem       1295  1294  0 09:43 pts/0    00:00:00  |           \_ -bash
bem       1314  1295  0 09:43 pts/0    00:00:00  |               \_ ps -aef --forest
root      1261   869  0 09:34 ?        00:00:00  \_ sshd: root@pts/1
root      1264  1261  0 09:34 pts/1    00:00:00      \_ -bash
root      1286  1264  0 09:36 pts/1    00:00:00          \_ top
```

Beschreibung der `ps` Felder

|Feld| Beschreibung|
|:--:|:--:|
|USER | user owning the process |
|PID | process ID of the process|
|PPID | parent process ID|
|%CPU | It is the CPU time used divided by the time the process has been running.|
|%MEM | ratio of the process’s resident set size to the physical memory on the machine|
|VSZ | virtual memory usage of entire process (in KiB)|
|RSS | resident set size, the non-swapped physical memory that a task has used (in KiB)|
|TTY | controlling tty (terminal)|
|STAT | multi-character process state|
|START | starting time or date of the process|
|TIME | cumulative CPU time|
|COMMAND | command with all its arguments|

#### Prozesse in *tree*  Darstellung

```
# pstree -psl
systemd(1)─┬─NetworkManager(623)─┬─dhclient(663)
           │                     ├─{NetworkManager}(636)
           │                     └─{NetworkManager}(641)
           ├─auditd(596)───{auditd}(597)
           ├─crond(635)
           ├─dbus-daemon(619)───{dbus-daemon}(621)
           ├─login(649)───bash(1105)
           ├─lvmetad(487)
           ├─master(1087)─┬─pickup(26764)
           │              └─qmgr(1092)
           ├─polkitd(618)─┬─{polkitd}(620)
           │              ├─{polkitd}(622)
           │              ├─{polkitd}(630)
           │              ├─{polkitd}(633)
           │              └─{polkitd}(637)
           ├─rsyslogd(853)─┬─{rsyslogd}(856)
           │               └─{rsyslogd}(857)
           ├─sshd(850)───sshd(1401)───bash(1405)─┬─find(27430)───strings(27743)
           │                                     └─pstree(27907)
           ├─systemd-journal(459)
           ├─systemd-logind(625)
           ├─systemd-udevd(494)
           └─tuned(849)─┬─{tuned}(1072)
                        ├─{tuned}(1073)
                        ├─{tuned}(1077)
                        └─{tuned}(1099)
```

## Prozesse steuern

### Foreground & Background

Einen im Vordergrund laufenden Prozess kann entweder mit `ctrl/c` oder durch senden eines entsprechenden Signals ( kill -3 ) auf die Prozess ID beendet werden.

Beispiel:

Den Prozess vom Kommande *dd* mit `ctrl/c` beendet.

```
#  dd if=/dev/zero of=/dev/null
^C906512+0 records in
906511+0 records out
464133632 bytes (464 MB) copied, 0.90896 s, 511 MB/s
```

Mit `ctrl/z` wird der Prozess gestoppt und in den Background versetzt.

```
#  dd if=/dev/zero of=/dev/null
^Z
[1]+  Stopped                 dd if=/dev/zero of=/dev/null

[root@w901s ~]# jobs
[1]+  Stopped                 dd if=/dev/zero of=/dev/null
```

Prozesse mir `&` im Background auszuführen

`# command &`

Background Prozesse auflisten

`jobs`

Backgroundprozesse in den Foreground bringen

`fg %<id>`

Background Prozess killen

`kill %<id>`

Background Prozess **forced** killen

`kill -9 %<id>`


### Prozesse mit **nuhup** starten

Wird der *parent* Prozess eines Prozesses beendet, so beendet sich in auch dessen *child* Prozess. Das ist beispielsweise der Fall, wenn eine *ssh* Verbindung beendet wird. In der Regel ist das so auch ganz ok, manchmal will man aber, dass ein Prozess auch dann noch weiterläuft, wenn die Verbindung unterbrochen wird (oder der *parent* Prozess aus einem anderen Grund beendet wurde). Das kann insbesondere bei *sehr lange laufenden Jobs* der Fall sein. In diesem Fall kann der Prozess mit **nohup** gestartet werden.

Folgendes Beispiel führt das Kommando `find` im Hintergrund aus und erstellt eine Liste der Filetypen im /tmp.
Mit der `nohup` Option wird der Befehl auch beim Schliessen des Session weiter ausgeführt.

` nohup find / -exec file {} \; >/tmp/files_on_system &`


### Prozesse priorisieren

Prozesse können entweder mit einer höheren oder einer geringeren Priorität ausgeführt werden.

Prozesse können mit einem *negativen* Nice Wert höher und mit einem *positiven* Wert tiefer priorisiert werden.
Der Range bei Linux liegt bei *-20* und *+19* . Im `top` sind die aktuellen *nice* Werte der Prozesse ersichtlich.

Beispiel - Priorität erhöhen

`renice -10 <PID>`

Beispiel - Priorität verringern

`renice +10 <PID`

**MERKE:** Durch die Leistungsfähigkeit moderner Systeme ist es heutzutage unüblich, die Prozessprioritäten anzupassen.

## die wichtigsten Signale

|Nummer| Name| Beschreibung|
|:--:|:--:|:--:|
|1 |HUP | Hangup|
|2 |INT | Interupt|
|3 |QUIT |QUIT |
|9 |KILL |Kill|
|15 |TERM |Software termination|
|17 |STOP |Stop|
|19|CONT| Continue after stop|

## wichtige Befehle

|Befehl | Bedeutung|
|:--:|--|
|top|Übersicht der laufenden Prozesse|
|ps|Listet Prozesse|
|pstree| Zeigt Prozesse als Baumstruktur (SW muss zusätzlich installiert werden)
|bg|sendet Job in den Background |
|fg|sended Job in den Foreground |
|jobs| listed Background Jobs|
|kill| sended das *kill* Signal zu einem Job|
|renice| Prozessprioritäten ändern|
|nohup| Prozess wird beim beenden des Parent Prozess nicht beendet|

## wichtige Files und Verzeichnisse
|File/Dir | Bedeutung|
|:--:|--|
|/procs| Mountpoint mit Runtime Informationen |

## weitere Infos
mehr zu diesem Thema finden sie [hier][1]
