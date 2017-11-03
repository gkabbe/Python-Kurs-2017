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


# Aufgabe Palindrom

Schreiben Sie eine Funktion _palindrom_, die überprüft, ob ein String ein Palindrom ist (also vorwärts und rückwärts gelesen das gleiche ergibt).


Beispiel:

```python
def palindrom(wort):
    ...

print(palindrom("anna"))
print(palindrom("anne"))
```

Ausgabe:

```
True
False
```

# Zahlen von 1 bis n

Schreiben Sie eine Funktion, die bei Eingabe einer natürlichen Zahl n die Zahlen von 1 bis n ausgibt.
Jedoch ohne eine Schleife zu benutzen!

# Matrix Multiplikation

Schreiben Sie eine Funktion mat_mul(matrix_a, matrix_b), die zwei Matrizen als Eingabe nimmt und ihr 
Produkt ausgibt.

Hinweis:

Eine Matrix können Sie als Liste von Listen speichern:

```python
mat = [[1, 0, 0],
       [0, 1, 0],
       [0, 0, 1]]
```

# Sichtbarkeit und Lebensdauer von Variablen in Funktionen

Was gibt folgender Code aus?
    
```python
x = 1
def f():
    print(x)
f()
```

Was passiert jetzt?

```python
x = 1
def f():
    x = 5
    print(x)
f()
print(x)
```

Und hier?

```python
def f():
    x = 5
f()
print(x)
```

Verschachtelt:

```python
x = 1
def f_außen():
    x = 5
    def f_innen():
        print(x)
    return f_innen

f_innen = f_außen()
f_innen()
```

???

```python
def f(liste=[]):
    liste.append(1)
    print(liste)
f()
f()
f()
f()
```
        

Versuchen Sie, die Resultate der einzelnen Code-Fragmente zu erklären!        

# Dictionaries

Dictionaries sind eine Datenstruktur, die Wertepaare speichert.
Zu jedem Schlüssel gibt es einen Wert, auf den man zugreifen kann wenn man den Schlüssel hat.

Beispiel:

```python
student = {"name": "Müller",
           "vorname": "Karl",
           "studiengang": "Physik"}


print(student["vorname"], student["name"], "studiert", student["studiengang"])

```


## Telefonbuch

Schreiben Sie ein (ganz kleines) Telefonbuch.
Für drei Nachnamen soll es jeweils die dazugehörige Telefonnummer speichern.


## Englisch-Deutsch Wörterbuch


Gegeben ist ein (zugegebenermaßen sehr knappes) Englisch-Deutsch-Wörterbuch:

```python
englisch_deutsch_dict = {"hello": "hallo", "world": "welt", "good bye": "auf wiedersehen"}
```

Machen Sie daraus ein Deutsch-Englisch-Wörterbuch!


## Aufgabe Cäsar Verschlüsselung

Die _Cäsar Verschlüsselung_ ist eine Verschlüsselung, bei der jeder Buchstabe des zu verschlüsselnden Textes mit einem anderen Buchstaben ersetzt wird, dessen Position im Alphabet um _n_ Buchstaben verschoben ist.  
Beispielsweise könnte man jeden Buchstaben um 4 Positionen verschieben:  

```
a -> e
b -> f
...
z -> d 
```

* Schreiben Sie eine Funktion, die für Wörter, die aus Kleinbuchstaben bestehen, die sogenannte _ROT13_ Verschlüsselung implementiert (also die Cäsar Verschlüsselung für n=13).

```python

def rot13(wort):
    ...


print(rot13("hallo welt"))
```

Ausgabe:

```
'unyyb jryg'
```
  
  * Hierfür ist es hilfreich, ein Dictionary zu erstellen, das jedem Buchstaben seinen "verschlüsselten" Buchstaben zuweist
  * Kleine Hilfe:
   
```python
alphabet = 'abcdefghijklmnopqrstuvwxyz'
```
    
Erstellen Sie nun daraus einen String alphabet_verschoben (Slicing hilft!), der mit dem 13. Buchstaben beginnt.

* Wie sieht die Funktion aus, die verschlüsselten Text wieder entschlüsselt?

# Pascalsches Dreieck

![PascalschesDreieck](https://upload.wikimedia.org/wikipedia/commons/0/0d/PascalTriangleAnimated2.gif)

(Quelle: https://de.wikipedia.org/wiki/Pascalsches_Dreieck)

Das Pascalsche Dreieck ist ein Dreieck aus Zahlen. In jeder Zeile sind die erste und die letzte Zahl jeweils Einsen. Für die weiteren Zahlen gilt folgende rekursive Formel:
z(zeile, i) = z(zeile-1, i-1) + z(zeile-1, i).

So gilt beispielsweise für die Zahl 6 (vierte Zeile) im obigen Dreieck: sie steht in der 4.Zeile (bei Null anfangen zu zählen!) an zweiter Stelle, und ist die Summe aus der Zahl in der 3. Zeile an erster Stelle und der Zahl in der 3. Zeile an zweiter Stelle.

Schreiben Sie eine Funktion pascal_zeile, die für eine gegebene Zeilennummer die Einträge des Pascalschen Dreiecks ausgibt.


# Theoretische Chemie

Gegeben ist eine sogenannte [xyz-Datei](https://raw.githubusercontent.com/gkabbe/Python-Kurs2015/master/%C3%9Cbungen/molecule-example.xyz), die eine Auflistung von Atomen und
ihren Positionen enthält.
In der ersten Zeile dieser Datei steht die Anzahl der Atome, die zweite Zeile enthält Kommentare.
Schließlich erfolgt die Auflistung.

Beantworten Sie folgende Fragen:

* Wieviel Wasserstoffatome (Buchstabe H) sind nicht mehr als 2.0 Angström (Längeneinheit, entspricht \\(10^{-10}\\) m) von einem Sauerstoffatom (O) entfernt?
* Wieviele Sauerstoffatome sitzen in der Nähe jedes Phosphoratoms (P)? 

