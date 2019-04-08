# mit Files und Fileinhalten arbeiten
Alle hier vorgestellten *Kommandos* sind sehr nützlich und meist auch sehr mächtige
Unix Tools. Die meisten haben eine Vielzahl von Optionen, welche jeweils den
Anforderungen der Aufgabe angepasst werden müssen. Hier werden lediglich die Tools
vorgestellt. Über jedes dieser Tools findet man im Internet haufenweise nützliche
Beispiele zu den verschiednenen Anforderunge.

## Filemanipulationen

### touch - leeres File erstellen

`touch <file>`

### cp - Kopieren
Einfaches Kopieren
`cp <file1> <file2>`

Kopieren mit absoluten Pfaden
`cp /var/<file1> /opt/<file2>`

Rekursiv Kopieren, kopiert alles, inkl. Unterverzeichnisen nach /tmp
`cp -R * /tmp/`

### mv - Moven

**Achtung:** mv kennt kein rekursiv, es werden *IMMER* alle Unterverzeichnise mitverschoben

Verschiebt *file1* nach *file2*
 `mv <file1> <file2>`
Verschiebt *dir1* nach */tmp*
`mv <dir1> /tmp/`

### ln - Symlink (Verknüpfung) erstellen

Syntax: `ln -s <Datei> <Symlink>`

```
$ ln -s realfile linkfile
$ ls -l
lrwxrwxrwx. 1 root root 8 May 23 15:49 linkfile -> realfile
-rw-r--r--. 1 root root 0 May 23 15:49 realfile
```

**Merke:** Ein *symlink* hat immer Permission rwxrwxrwx (oder 777). Das bedeutet aber nicht,
dass auch diese Permission gelten. Die Permission werden vom original File übernommen.


## Ausgaben

### cat
Fileinhalt ausgeben
```
$ cat kantone
Kanton;qkm;Einwohner;Hauptort
Graubuenden;7105;196600;Chur
Bern;5959;1017200;Bern
Wallis;5224;335600;Sitten
Waadt;3212;773200;Lausanne
Tessin;2812;352900;Bellinzona
St. Gallen;2026;499000;St. Gallen
Zuerich;1729;1466000;Zuerich
Freiburg;1671;307400;Freiburg
Luzern;1493;398700;Luzern
Aargau;1404;653500;Aargau
Uri;1077;36000;Altdorf
Thurgau;991;267400;Frauenfeld
Schwyz;908;154100;Schwyz
Jura;838;72800;Delsberg
Neuenburg;803;178100;Neuenburg
Solothurn;791;266400;Solothurn
Glarus;685;40000;Glarus
Basel-Landschaft;518;283200;Liestal
Obwalden;491;37100;Sarnen
Schaffhausen;298;79800;Schaffhausen
Genf;282;484400;Genf
Nidwalden;276;42400;Stans
Appenzell Ausserrhoden;243;54500;Herisau
Zug;239;122100;Zug
Appenzell Innerrhoden;173;16000;Appenzell
Basel-Stadt;37;191800;Basel
```

### tail

Inhalt vom Dateiende her ausgeben

`tail -f <datei>` printet den Dateiinhalt in Echtzeit, nützlich bei Logdateien

Beispiel: die letzen 5 Zeilen

```
$ tail -5 kantone
Nidwalden;276;42400;Stans
Appenzell Ausserrhoden;243;54500;Herisau
Zug;239;122100;Zug
Appenzell Innerrhoden;173;16000;Appenzell
Basel-Stadt;37;191800;Basel
```

### head

Inhalt vom Dateianfang her ausgeben
Beispiel: die ersten 3 Zeilen

```
$ head -3 kantone
Kanton;qkm;Einwohner;Hauptort
Graubuenden;7105;196600;Chur
Bern;5959;1017200;Bern
```

### less / more

Gibt den Dateiinhalt Seitenweise aus. Mit [PageUP] [PageDown] kann innerhalb der Datei
navigiert werden.

`more <datei>` oder `less <Datei>`


### grep

Ausgabe von zeilen mit bestimmten Textmustern

```
$ grep Ap kantone
Appenzell Ausserrhoden;243;54500;Herisau
Appenzell Innerrhoden;173;16000;Appenzell
```


## Manipulationen

### sort

Mit *sort* kann der Output sortiert werden

Beispiel: nach Einwohner sortiert

```
$ sort -n -k3 -t';' kantone
Kanton;qkm;Einwohner;Hauptort
Appenzell Innerrhoden;173;16000;Appenzell
Uri;1077;36000;Altdorf
Obwalden;491;37100;Sarnen
Glarus;685;40000;Glarus
Nidwalden;276;42400;Stans
Appenzell Ausserrhoden;243;54500;Herisau
Jura;838;72800;Delsberg
Schaffhausen;298;79800;Schaffhausen
Zug;239;122100;Zug
Schwyz;908;154100;Schwyz
Neuenburg;803;178100;Neuenburg
Basel-Stadt;37;191800;Basel
Graubuenden;7105;196600;Chur
Solothurn;791;266400;Solothurn
Thurgau;991;267400;Frauenfeld
Basel-Landschaft;518;283200;Liestal
Freiburg;1671;307400;Freiburg
Wallis;5224;335600;Sitten
Tessin;2812;352900;Bellinzona
Luzern;1493;398700;Luzern
Genf;282;484400;Genf
St. Gallen;2026;499000;St. Gallen
Aargau;1404;653500;Aargau
Waadt;3212;773200;Lausanne
Bern;5959;1017200;Bern
Zuerich;1729;1466000;Zuerich
```

### tr

*tr* liest den standard Input und ändert oder löscht Charakter(klassen).
Mit *tr* kann  beispielsweise Text von lower- nach upper-Case transformiert werden.

Beispiel: lower nach upper Case transformieren

```
$ cat kantone |tr "[:lower:]" "[:upper:]"
KANTON;QKM;EINWOHNER;HAUPTORT
GRAUBUENDEN;7105;196600;CHUR
BERN;5959;1017200;BERN
WALLIS;5224;335600;SITTEN
WAADT;3212;773200;LAUSANNE
TESSIN;2812;352900;BELLINZONA
ST. GALLEN;2026;499000;ST. GALLEN
ZUERICH;1729;1466000;ZUERICH
FREIBURG;1671;307400;FREIBURG
LUZERN;1493;398700;LUZERN
AARGAU;1404;653500;AARGAU
URI;1077;36000;ALTDORF
THURGAU;991;267400;FRAUENFELD
SCHWYZ;908;154100;SCHWYZ
JURA;838;72800;DELSBERG
NEUENBURG;803;178100;NEUENBURG
SOLOTHURN;791;266400;SOLOTHURN
GLARUS;685;40000;GLARUS
BASEL-LANDSCHAFT;518;283200;LIESTAL
OBWALDEN;491;37100;SARNEN
SCHAFFHAUSEN;298;79800;SCHAFFHAUSEN
GENF;282;484400;GENF
NIDWALDEN;276;42400;STANS
APPENZELL AUSSERRHODEN;243;54500;HERISAU
ZUG;239;122100;ZUG
APPENZELL INNERRHODEN;173;16000;APPENZELL
BASEL-STADT;37;191800;BASEL
```

### cut

Entfernt bzw. gibt bestimmte Teile von einem Text aus.

Beispiel: Ausgabe Kantonname und der Anzahl Einwohner aus der Datei *kanton*

```
$ cut -d ';' -f 1,3 kantone
Kanton;Einwohner
Graubuenden;196600
Bern;1017200
Wallis;335600
Waadt;773200
Tessin;352900
St. Gallen;499000
Zuerich;1466000
Freiburg;307400
Luzern;398700
Aargau;653500
Uri;36000
Thurgau;267400
Schwyz;154100
Jura;72800
Neuenburg;178100
Solothurn;266400
Glarus;40000
Basel-Landschaft;283200
Obwalden;37100
Schaffhausen;79800
Genf;484400
Nidwalden;42400
Appenzell Ausserrhoden;54500
Zug;122100
Appenzell Innerrhoden;16000
Basel-Stadt;191800
```
