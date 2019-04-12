[1]: https://www.tuxcademy.org/download/de/grd1/grd1-de-manual.pdf#chapter.82
# der VI Editor

Der VI (oder auch VIM) ist ein sehr mächtiger Editor. Der Vorteil von **vi**, er ist
auf jedem Linux System verfügbar. Es lohnt sich daher, die wichtigsten Befehle von **vi**
zu beherrschen. Das ist insbesondere auch beim Troubleshooting wichtig, da hier
optionale Editoren wie etwa der **nano** oft nicht zur Verfügung stehen.

## die wichtigsten vi Befehle

### Editier & Command Modus
|Befehl|Funktion|
|:--:|--|
|i|startet den „Insert Modus“|
|ESC|Beendet den Insert Modus, jetzt können weitere Befehle eingegeben werden|
|:   | wechselt in den Command Modus |

### Text bearbeiten
|Befehl|Funktion|
|:--:|--|
| w |Springt zum Anfang des nächsten Wortes |
| B |Springt zum Anfang des letzten Wortes|
| e | Springt zum Ende des nächsten Wortes |
| G | Springt zum Ende der Datei |
| x |  Löscht das aktuelle Zeichen|
| 5x | Löscht die nächsten 5 Zeichen (andere Zahlen möglich!) |
| dd |Löscht die ganze Zeile (und kopiert sie in den Speicher)  |
| u | Undo: Macht die letzte Änderung rückgängig |
| . | Redo: Wiederholt die letzte Änderung |

### Dateie bearbeiten (speicher/schliessen)
|Befehl|Funktion|
|:--:|--|
|:q|vi beenden|
|:q!|vi beenden ohne speichern|
|:w|Datei speichern |
|:wq|Datei speichern und vi beenden |
|:w Datei|Datei speichern unter Dateiname «Datei» |

### Suchen & Ersetzen
|Befehl|Funktion|
|:--:|--|
|/String_zum_suchen | Sucht nach String_zum_suchen“ Richtung Dateiende|
| ?String_zum_Suchen |Sucht nach „String_zum_suchen“ Richtung Dateianfang |
| n|Sucht die nächste Fundstelle in Suchrichtung |
|:% s/abc/efd/g |Sucht und ersetzt im Ganzen Dokument (%) nach abc und ersetzt jedes Vorkommnis mit efg. Das "g" steht für "global" |
| :5,10 s/abc/efd/g|Sucht und ersetzt abc durch efd in den Zeilen 5-10 |
| :5,10 s/abc/efd/|Sucht und ersetzt das erste Vorkomnis von abc durch efd in den Zeilen 5-10 |

### Weiter Funktionen
|Befehl|Funktion|
|:--:|--|
|:set nu |Einschaltern der Zeilennummern |
|:set nonu |Ausschalten der Zeilennummern |
|:35 |springt auf Zeile 35 |
| :set list|Zeigt auch Steuerzeichen wie "tab" oder "spaces" an|
| :set nolist|schaltet Steuerzeichen ansicht wieder aus|

## weitere Infos
mehr zu diesem Thema finden sie [hier][1]
