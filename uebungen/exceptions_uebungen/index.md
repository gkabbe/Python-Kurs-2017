<!-- 
.. title: 6 - Übungen - 24.11.17
.. slug: exceptions_uebungen
.. date: 2017-11-23 00:00:00 UTC+01:00
.. tags: 
.. category: 
.. link: 
.. description: 
.. type: text
-->


# Mit Fehlern umgehen lernen

Wichtige Lektionen fürs Leben und für Python


## Auf Exceptions reagieren

### Input - 1

Folgendes Programm ist gegeben:


```python
while True:
    zahl1 = input("Bitte eine Zahl eingeben: ")
    zahl2 = input("Bitte noch eine Zahl eingeben: ")
    
    print("Die Summe ist", float(zahl1) + float(zahl2))
```

Dieses Programm funktioniert problemlos, solange sich der User an die Regeln hält und Zahlen
eingibt. 
Was passiert aber wenn die Eingabe etwas anderes ist?

Um auf solche Probleme reagieren zu können, gibt es in Python sogenannte try-Except Blöcke.

Beispiel:

```python
x = "text"

try:
    zahl = int(x)
except ValueError:
    print("Das war keine Zahl!")
```

Schreiben Sie das erste Programm so um, dass es nicht mit einem Fehler abbricht, sondern sich nur
beschwert, dass der Input des Users nicht korrekt war.

### Input - 2

Dieses Programm ist ähnlich wie das erste, teilt aber die zwei Zahlen durcheinander:

```python
while True:
    zahl1 = input("Bitte eine Zahl eingeben: ")
    zahl2 = input("Bitte noch eine Zahl eingeben: ")
    
    print("Die Summe ist", float(zahl1) / float(zahl2))
```

Gibt es eine Möglichkeit, das Programm zum Absturz zu bringen, auch wenn beide Inputs Zahlen sind?
Schreiben Sie es so um, dass es nicht mehr abstürzen kann.


## Eine Exception auslösen

Wir hatten die Fakultätsfunktion folgendermaßen geschrieben:


```python
def fak(n):
    if n == 0:
        return 1
    return n * fak(n - 1)
```

Sie funktioniert problemlos, solange der User ganze Zahlen größer gleich Null eingibt, bei negativen
Zahlen findet sie jedoch keinen Rekursionsanker und läuft daher immer weiter.

Mittels ```raise ...``` können Sie selbst in Ihrem Code eine Exception auslösen.
(Eine Übersicht aller Exceptions finden Sie [hier](https://docs.python.org/3/library/exceptions.html#bltin-exceptions))

* Prüfen Sie, ob die Eingabe kleiner Null ist, und lösen Sie in diesem Fall einen ValueError aus!

* Prüfen Sie auch, ob es sich um einen Integer handelt, und lösen Sie ebenfalls einen ValueError aus,
falls dies nicht der Fall ist.



# Dictionaries

## Studenten-Konstruktor

Schreiben Sie eine Funktion ```create_student```, die drei Parameter vorname, name und notenliste
erwartet, und ein Dictionary zurückgibt.


## json

Mit json können Sie Datenstrukturen aus Python (Listen, Dictionaries, Listen von Dictionaries etc.)
in lesbarem Format in Dateien speichern, und daraus wieder lesen.


Speichern Sie die Datei https://raw.githubusercontent.com/gkabbe/Python-Kurs-2017/src/extras/studenten.json
auf Ihrem Rechner

Betrachten Sie sie mit einem Texteditor.

Folgendermaßen können Sie sie in Python einlesen:

```python
import json

with open("studenten.json", "r") as f:
    studenten = json.load(f)
```

Analysieren Sie nun die Liste von Studenten.

* Schreiben Sie eine Funktion ```durchschnitts_note```, die für einen Studenten seine Durchschnittsnote berechnet

* Lassen Sie sich für die ersten drei Studenten ihre Durchschnittsnote berechnen

* Lassen Sie sich nun den Studenten mit dem besten Durchschnitt und dem schlechtesten ausgeben.
  Das geht folgendermaßen: Sie können allen vergleichenden Funktionen (min, max, sorted, ...)
  Ein spezielles Keyword namens key mitgeben.
  Nehmen Sie als key Ihre Durchschnittsnoten-Funktion
  
```python
bester_student = min(studenten, key=durchschnitts_note)
```
  
  Die Funktion min nimmt in diesem Fall die Durchschnittsnote als Vergleichswert, um das Minimum
  zu bestimmen.
  
* Sortieren Sie nun die Liste der Studenten nach Durchschnittsnote

* Schreiben Sie eine weitere Funktion, um mithilfe von key=... nach dem Nachnamen sortieren zu können

* Kreieren Sie eine Liste aller Vornamen und eine Liste aller Nachnamen. Zählen Sie die Häufigkeit
  jedes Namens

## if-else

Ihr Programmierkollege hat folgende Funktion geschrieben, die je nach User einen anderen String
zurückgibt:

```python
def gib_user_etwas(name):
    if name == "Müller":
        return "Gehaltsabrechnung"
    elif name == "Mayer":
        return "Steuerbescheid"
    elif name == "Schmidt":
        return "Abmahnung"
    elif name == "Huber":
        return "Gehaltserhöhung"
    else:
        return None
```

Schreiben Sie die Funktion neu, sodass sie statt if-elif-else ein Dictionary benutzt.

