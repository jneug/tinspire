Ein LaTeX-Paket als Ergänzung zum [schule-Paket](https://www.ctan.org/pkg/schule?lang=de).

Das Paket ergänzt viele Makros und Hilfen, um Dokumente für die Schule zu setzen. Dabei passt es das Schule-Paket auf meine eigenen Vorlieben an, die nicht unbedingt für alle sinnvoll sind. Trotzdem können die Quelldateien anderen vielleicht als Grundlage für eigene Anpassungen dienen.

Teile lassen sich einfach in eigene TeX-Dateien übernehmen oder sind als komplett eigenständige Pakete angelegt. So zum Beispiel das Paket [`tinspire.sty`](tinspire.sty), um Tasten des TI-nspire Taschenrechners setzen zu können.

## Installation
Alle Dateien müssen der TeX-Distribution zur Verfügung gestellt werden. Dazu gibt es verschiedene Möglichkeiten. Entweder alles liegt im selben Ordner wie die TeX-Dateien. die erstellt werden, was aber den Nachteil hat, dass die Überischt schnell verloren geht. Bei mir, unter macOS Mojave und MacTeX, liegt alles im Ordner `~/Library/texmf/tex`. Dann haben alle TeX-Dateien Zugriff auf die Pakete. Für andere Distributionen und Betriebssysteme hilft ein Blick in die Dokumentation.

## Dateien

* [`vorschule.sty`](vorschule.sty) modifiziert einige Optionen von Paketen, die von schule geladen werden. Daher muss das Paket vor schule mit `\usepackage{vorschule}` eingebunden werden.
* [`ngbschule.sty`](ngbschule.sty) übernimmt den Hauptteil der Modifikationen. Sie bekommt einige Optionen ähnlich zum schule-Paket. Außerdem werden weitere Dateien basierend auf der Konfiguration von schule geladen. Zum Beispiel wird (falls vorhanden) die Datei `ngb/<Fach>.tex` geladen, um Erweiterungen für bestimmte Fächer nachzuladen. Genauso wird `ngb/<Typ>.tex` geladen, für spezielle Makros pro Dokumenttyp (z.B. Arbeitsblatt oder Klausur). Ist die Option `typ` auch beim Laden des Pakets `ngbschule` angegeben, wird der Dokumenttyp von `schule` durch den neuen überschrieben. So können auch Zusatzerweiterungen geladen werden. Z.B. für einen Checkup-Bogen zur Klausurvorbereitung.

```
\usepackage[
	typ=<subtyp>,
	autor=<Autor>,
	kuerzel=<Kuerzel des Autors>,
	titel=<Titel>,
	reihe=<Unterrichtsreihe>,
	datum=<Datum>,
	ohneLochung
]{ngbschule}
```