<!-- 
.. title: 3 - Funktionen, Klassen und Objekte - Übungen
.. slug: funktionen_klassen_objekte_uebungen
.. date: 2017-05-11 00:00:00 UTC+01:00
.. tags: 
.. category: 
.. link: 
.. description: 
.. type: text
-->

# Aufgabe max

* Schreiben Sie eine Funktion die für zwei gegebene Zahlen die größere zurückgibt
* Schreiben Sie eine Funktion, die für eine Liste von Zahlen die größte zurückgibt

# Aufgabe Listen

Gegeben sind eine Funktion und eine Liste

```python
def f(x):
    return 1 / x

numbers = list(range(1, 21))
```

Wenden Sie die Funktion auf jedes Element der Liste an.

# Aufgabe Palindrom

Schreiben Sie eine Funktion _palindrom_, die überprüft, ob ein String ein Palindrom ist (also vorwärts und rückwärts gelesen das gleiche ergibt).

Implementieren Sie diese Funktion sowohl iterativ, als auch rekursiv!

# Ein- und Ausgabe

## read_file

Schreiben Sie eine Funktion _read_file_, die einen Dateinamen als Argument erwartet und eine Liste mit den Zeilen der ausgelesenen Datei zurückgibt

## write_file

Schreiben Sie eine Funktion _write_file_, die als Argumente einen Dateinamen, sowie eine Liste mit Strings erwartet und diese in eine Datei schreibt.

# Zahlen von 1 bis n

Schreiben Sie eine Funktion, die bei Eingabe einer natürlichen Zahl n die Zahlen von 1 bis n ausgibt.
Jedoch ohne eine Schleife zu benutzen!

# Matrix Multiplikation

Schreiben Sie eine Funktion mat_mul(matrix_a, matrix_b), die zwei Matrizen als Eingabe nimmt und ihr Produkt ausgibt.

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
def f_aussen():
    x = 5
    def f_innen():
        print(x)
    return f_innen

f_innen = f_aussen()
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


# Aufgabe Cäsar Verschlüsselung

Die _Cäsar Verschlüsselung_ ist eine Verschlüsselung, bei der jeder Buchstabe des zu verschlüsselnden Textes mit einem anderen Buchstaben ersetzt wird, dessen Position im Alphabet um _n_ verschoben ist.  
Beispielsweise könnte man jeden Buchstaben um 4 Positionen verschieben:  

```
a -> e
b -> f
...
z -> d 
```

* Schreiben Sie eine Funktion, die für Wörter, die aus Kleinbuchstaben bestehen, die sogenannte _ROT13_ Verschlüsselung implementiert (also die Cäsar Verschlüsselung für n=13).

```python
rot13("hallo welt")
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

# Klassen

Schreiben Sie eine Klasse Student mit folgenden Eigenschaften:

* Ein neues Studenten-Objekt wird erstellt, indem man dem Konstruktor (d.h. der __init__ Funktion Namen und Vornamen des Studenten übergibt:

```python
student = Student(name="Müller", vorname="Heinz")
```

* Die Klasse soll eine Objektvariable _noten_liste_ besitzen, die zu Beginn eine leere Liste ist, sowie eine Methode _neue_note_, die der _noten_liste_ eine neue Note hinzufügt

* Schreiben Sie eine Methode _durchschnitts_note_, die den Durchschnitt aller Noten in _noten_liste_ bildet
