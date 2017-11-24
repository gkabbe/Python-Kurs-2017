<!-- 
.. title: 5 - Übungen - 17.11.17
.. slug: module_exceptions_uebungen
.. date: 2017-11-16 00:00:00 UTC+01:00
.. tags: 
.. category: 
.. link: 
.. description: 
.. type: text
-->



# Module

## time

Das time Modul bietet verschiedene Funktionen zur Zeitmessung an.

Die Funktion time.time() gibt Ihnen die Anzahl Sekunden seit dem Jahr 1970 zurück.

* Schreiben Sie ein Programm, das als Stoppuhr fungiert. Wenn Sie das erste Mal eine Taste drücken,
startet der Timer. Beim Zweiten Drücken wird die vergangene Zeit in Sekunden ausgegeben.

Die Funktion time.sleep() erwartet als Parameter eine Zahl, die angibt, wieviel Sekunden "geschlafen"
werden soll. In dieser Zeit tut das Programm nichts.

* Schreiben Sie ein Programm "echo", das auf Input vom User wartet, dann eine Sekunde schläft, und
das Input wieder ausgibt.

## random

Das Modul random bietet diverse Funktionen an, mit denen man Zufallszahlen generieren kann.

### Würfel

Schreiben Sie ein Programm, das den Wurf einen sechsseitigen Würfels simuliert.
Benutzen Sie dafür random.randrange.

Berechnen Sie die durchschnittliche geworfene Augenzahl nach 1000 Spielen.

### Lotto

Spielen Sie Lotto! (aber nur am Computer...) 

* Schreiben Sie eine Funktion ```zieh_sechs```, die 6 Kugeln aus 49 zieht und das Ergebnis in einer Liste zurückgibt.
  Benutzen Sie dafür die Funktion ```random.choice```, mit der Sie zufällig eine Zahl aus einer Liste
  auswählen können.

* Schreiben Sie nun ein Programm, das eine Million mal Lotto spielt.
  Definieren Sie dafür zuerst eine Funktion ```spiel_lotto```.
  Diese erzeugt zwei Listen, indem sie ```zieh_sechs``` zweimal aufruft.
  Dann werden beide Listen verglichen und die gemeinsamen Zahlen gezählt.
  Der Rückgabewert ist die Anzahl der richtig gezogenen Zahlen.

* In wieviel Prozent der Fälle gibt es 1 (2, ..., 6) richtige Treffer?


## datetime

Das Modul datetime bietet viele verschiedene Möglichkeiten, mit Kalenderdaten umzugehen.
Um es zu importieren, schreiben Sie

```python
from datetime import datetime
```

Mithilfe von ```jetzt = datetime.now()``` können Sie sich ein datetime-Objekt zurückgeben lassen mit der 
aktuellen Zeit.
Mittels ```jetzt.day```, ```jetzt.month``` usw. können Sie sich Werte für Tag, Monat, Jahr etc. geben lassen.

* Benutzen Sie am besten Jupyter oder IPython, um sich interaktiv Informationen über *jetzt* zu verschaffen

* Kreieren Sie ein zweites datetime-Objekt *danach* mit datetime.now(). Bilden Sie die Differenz
  der zwei datetime-Objekte und speichern Sie sie unter dem Namen *delta*. Welchen Typ hat *delta*?

* Benutzen Sie jetzt.weekday(), um sich den aktuellen Wochentag ausgeben zu lassen. Die Ausgabe ist eine
  Zahl zwischen 0 und 6. Schreiben Sie eine Funktion, die statt der Zahl den Wochentag als String
  ausgibt.

## Vom eigenen Skript importieren

```import``` funktioniert nicht nur mit Modulen aus der Standardlibrary.
Sie können damit auch einfach eigene Objekte aus ihren eigenen Skripten laden.


* Schreiben Sie als erstes eine Python-Datei library.py, in der sie eine Funktion ```meine_fkt``` definieren 
  (was die macht, ist Ihnen überlassen)

* Schreiben Sie dann eine zweite Datei *main.py* im selben Ordner wie library.py.
  Importieren Sie in dieser ihr libary.py Skript mit

```python
import library
```

* Versuchen Sie nun, Ihre Funktion aufzurufen

* Schreiben Sie in library.py in eine Zeile (außerhalb der Funktion) einen print-Befehl. 
  Führen Sie nun nochmal main.py aus



