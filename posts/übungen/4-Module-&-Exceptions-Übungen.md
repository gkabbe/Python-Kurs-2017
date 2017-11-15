<!-- 
.. title: 5 - Übungen - 17.11.
.. slug: module_exceptions_uebungen
.. date: 2018-11-10 00:00:00 UTC+01:00
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

### Lotto

Spielen Sie Lotto! (aber nur am Computer...) 

* Schreiben Sie ein Programm, das 6 Kugeln aus 49 zieht.
  Benutzen Sie dafür die Funktion ```random.choice```, mit der Sie zufällig eine Zahl aus einer Liste
  auswählen können.

* Schreiben Sie ein Programm, das eine Million mal Lotto spielt.
Dafür brauchen Sie eine Funktion ```spiel_lotto```.
In dieser Funktion wird zuerst die Ziehung simuliert.
Danach zieht der Computer 6 Zahlen, und es wird verglichen, wieviele davon mit der Ziehung
übereinstimmen.
Der Rückgabewert ist dann die Anzahl der richtig gezogenen Zahlen.

* In wieviel Prozent der Fälle gibt es 1 (2, ..., 6) richtige Treffer?


## datetime

Das Modul datetime bietet viele verschiedene Möglichkeiten, mit Kalenderdaten umzugehen.
Um es zu importieren, schreiben Sie

```python
from datetime import datetime
```

Mithilfe von ```x = datetime.now()``` können Sie sich ein datetime-Objekt zurückgeben lassen mit der 
aktuellen Zeit.
Mittels ```x.day```, ```x.month``` usw. können Sie sich Werte für Tag, Monat, Jahr etc. geben lassen.

* Benutzen Sie x.weekday(), um sich den aktuellen Wochentag ausgeben zu lassen. Die Ausgabe ist eine
  Zahl zwischen 0 und 6. Schreiben Sie eine Funktion, die statt der Zahl den Wochentag als String
  ausgibt.


## json

Mit json können Sie Datenstrukturen aus Python (Listen, Dictionaries, Listen von Dictionaries etc.)
in lesbarem Format in Dateien speichern, und daraus wieder lesen.




