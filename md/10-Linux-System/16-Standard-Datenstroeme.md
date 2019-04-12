[1]: https://www.tuxcademy.org/download/de/lxk1/lxk1-de-manual.pdf#chapter.169
# Standard-Datenströme

Unix Systeme kennen verschiedene Datenströme für Daten Ein- und Ausgaben. Dazu werden sogenannte Kanäle verwendet.

+ Kanal 1 = Standard Ausgabe (stdout)

+ Kanal 2 = Standard Fehlerkanal (stderr)

Die Datenströme können mit *Umleitungen* auch sogenannte *redirects* beeinflusst werden um beispielsweise in ein File oder ein Device umgeleitet werden.


## Ein- und Ausgaben

### STDIN - standard Eingabe (Input)

Mit der Standard Eingaben können Daten in ein Programm eingelesen werden.

> $ cat < /etc/passwd


### STDOUT - Standard Ausgabe (Output)

Ein Programm nützt die Standard Ausgabe, auch **STDOUT** um reguläre Ausgaben zu tätigen. Das ist der **Kanal 1**. Meist ist das ein Terminal

In diesem Beispiel wird der Inhalt der Datei /etc/passwd an das Terminal geleitet

> $ cat /etc/passwd

Hier wird der Inhalt der Datei /etc/passwd in die Datei /tmp/user umgeleitet.

> $ cat /etc/passwd > /tmp/user

### STDERR - Standard Error

Ein Programm nützt die Standard Error Ausgabe, auch **STDERR** um Fehlermeldungen zu senden. Das ist der **Kanal 2**. Meist werden diese ebenfalls wie die Standard Ausgabe an das Terminal gesendet. Sie können aber auch gesondert in ein Datei umgeleitet werden oder sogar ganz unterdrückt werden, indem sie an das virtuelle Device */dev/null* umgeleitet werden.

```
$ ls not-exist
ls: cannot access not-exist: No such file or directory
```

Hier wird ein `ls` auf eine nichtexistierende Datei gemacht. Die Fehlermeldung wird auf das Terminal geschrieben.

```
$ ls not-exist 2> /dev/null
$
```

Hier wird ebenfalls ein `ls` auf eine nicht existierende Datei gemacht, jedoch wird diesmal mit `2>` Kanal 2 nach /dev/null umgeleitet. Somit erscheint keine Fehlerausgabe auf dem Terminal.

## Umleitungen

## Eingabe Umleiten

Die einfachste Arte eine Eingabe umzuleiten ist mit `<` .

> $ cat < /etc/passwd


Eine weiter Art ist mit **EOF**

```
command <<EOF
> Zeile 1
> Zeile 2
> Zeile 3
> Zeile N
> EOF
```

Dies übergibt dem Programm command die Zeilen 1 bis N in dieser Reihenfolge, jeweils als eigenständige Eingabe. Beim Schlüsselwort EOF wird die Eingabeumleitung beendet. Statt EOF kann man nahezu beliebige Schlüsselwörter verwenden, EOF hat sich aber eingebürgert. Eine konkrete Anwendung könnte zum Beispiel ein Backup einer MySQL-Datenbank sein.

```
mysql -uUSER -pPASSWORD <<EOF
flush tables with read lock;
system lvcreate -l100%FREE -s -n dbbackup /dev/vgmysql/mysql;
unlock tables;
EOF
```

Dieser Aufruf sperrt die Datenbank für Schreibzugriffe, erstellt durch einen MySQL-internen Systemaufruf einen LVM-Snapshot an angegebener Position, und gibt die Tabellen wieder frei. Mittels weiterer Programme kann nun mit dem Snapshot gearbeitet werden (Backup erstellen, etc.), ohne, dass die eigentliche Tabelle beeinflusst wird.

Per Eingabeumleitung werden hier drei Befehle an den MySQL-client gesendet. Dieser interpretiert die Befehle so, als wenn sie direkt eingegeben worden wären.

```
cat << EOF > /tmp/textfile
Dieser Text wird nach
     --> /tmp/textfile
geschrieben
EOF
```

Dieses Beispiel schreibt einen Text in ein File

```
cat << EOF >> /tmp/textfile
Dieser Text wird nach
     --> /tmp/textfile
geschrieben
EOF
```

Dieses Beispiel fügt den Text am Ende des Files zu.

### Ausgabe Umleitungen

Der einfachste Fall einer Ausgabeumleitung ist das Umleiten von STDOUT in eine Textdatei, um so zum Beispiel eine Dateiliste zu erhalten.

> $ ls -al > output

Mit der Umleitung `>` wird immer mit einer neuen Datei begonnen. Existiert die Datei bereits, so werden vorhandene Daten in der Datei gelöscht.

Um Text an eine bestehend (oder auch neue) Datei anzuhängen, wird `>>` verwendet.

> $ ls -al >> output

STDERR nach STDOUT umleiten

> $ command 2>&1

STDOUT nach STDERR umleiten

> $ command 1>&2



```
command 2>&1> /dev/null
command > /dev/null 2>&1
```

Dies leitet STDERR nach STDOUT um. STDOUT wird nach /dev/null umgeleitet. Das Resultat ist, dass weder Standard-Meldungen noch Fehlermeldungen von command ausgegeben werden.

Die zweite Zeile ist eine gängige, alternative Schreibweise dieses Aufrufs. Durch > /dev/null wird die STDOUT nach /dev/null geleitet, durch 2>&1 wird STDERR nach STDOUT geleitet (das ja nach /dev/null geleitet wird).

## PIPES

Mittels Pipes wird die Ausgabe eines Programms an ein anderes Programm weitergereicht.  

> $ cat file | grep Inhalt

Die Kombination `cat | grep` wird in der Praxis oft gesehen, ist aber eigentlich unnötig, da **grep** direkt auf die Datei angewendet werden kann.

> $ grep Inhalt <Datei>


## wichtige Files und Verzeichnisse
|File/Dir | Bedeutung|
|:--:|--|
|/dev/stdin/|Device für STDIN|
|/dev/stdout/|Device für STDOUT|
|/dev/stderr/|Device für STDERR|
|/dev/null/|Device für <Entsorgen>|

## weitere Infos
mehr zu diesem Thema finden sie [hier][1]
