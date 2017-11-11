<!-- 
.. title: 3 - Übungen - 3.11.17
.. slug: funktionen_klassen_objekte_uebungen
.. date: 2017-11-03 00:00:00 UTC+01:00
.. tags: 
.. category: 
.. link: 
.. description: 
.. type: text
-->

# Funktionen

## Hallo, name!

Schreiben Sie eine Funktion "hallo", die als Parameter einen Namen erwartet, und bei Aufruf diesen
grüßt.

```python
def hallo(name):
    ...
```

Beispiel:

```python
hallo("Karl")
```

Ausgabe:

```
Hallo, Karl!
```


## Aufgabe maximum

* Schreiben Sie eine Funktion _maximum_ die für zwei gegebene Zahlen die größere zurückgibt
* Schreiben Sie eine Funktion *listen_maximum*, die für eine Liste von Zahlen die größte zurückgibt

# Listen

## Funktion auf Liste anwenden

Gegeben sind eine Funktion und eine Liste

```python
def f(x):
    return 1 / x

numbers = list(range(1, 21))
```

Wenden Sie die Funktion auf jedes Element der Liste an und speichern Sie die Ergebnisse in einer
neuen Liste.


## Liste filtern

Ein Zoo besitzt eine [Liste von Tieren](https://raw.githubusercontent.com/gkabbe/Python-Kurs-2017/src/extras/tierliste)

* Benutzen Sie eine List Comprehension, um eine Liste aller Tiere zu erstellen, die mit "A" anfangen

* Erstellen Sie eine Liste aller Fische (also aller Tiere, die "Fisch" im Namen haben)

* Erstellen Sie nun für jeden Buchstaben im Alphabet eine Liste von Tieren, die mit diesem Buchstaben
anfangen

* Bonus: Erstellen Sie ein Dictionary, das für den entsprechenden Anfangsbuchstaben die zuvor erstellte
Liste zurückgibt

# Ein- und Ausgabe

## read_file

Schreiben Sie eine Funktion _read_file_, die einen Dateinamen als Argument erwartet und eine Liste mit den Zeilen der ausgelesenen Datei zurückgibt

## write_file

Schreiben Sie eine Funktion _write_file_, die als Argumente einen Dateinamen, sowie eine Liste mit Strings erwartet und diese in eine Datei schreibt.


# Theoretische Chemie

Gegeben ist eine sogenannte [xyz-Datei](https://raw.githubusercontent.com/gkabbe/Python-Kurs2015/master/%C3%9Cbungen/molecule-example.xyz), die eine Auflistung von Atomen und
ihren Positionen enthält.
In der ersten Zeile dieser Datei steht die Anzahl der Atome, die zweite Zeile enthält Kommentare.
Schließlich erfolgt die Auflistung der Atome. Dabei besteht jede Zeile aus dem Atomnamen und der Position in
x-, y- und z-Richtung.

Beantworten Sie folgende Fragen:

* Wieviel Wasserstoffatome (Buchstabe H) sind nicht mehr als 2.0 Angström (Längeneinheit, entspricht \\(10^{-10}\\) m) von einem Sauerstoffatom (O) entfernt?
* Wieviele Sauerstoffatome sitzen in der Nähe jedes Phosphoratoms (P)? 

