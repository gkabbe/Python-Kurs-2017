<!-- 
.. title: 4 - Übungen - 10.11.17
.. slug: funktionen_dictionaries
.. date: 2017-11-09 00:00:00 UTC+01:00
.. tags: mathjax
.. category: 
.. link: 
.. description: 
.. type: text
-->

# Funktionen

## Sichtbarkeit (Scope) von Variablen in Funktionen

Python unterscheidet zwischen globalen und lokalen Variablen.
Globale Variablen sind Variablen, die auf der obersten Ebene des Python-Skripts definiert wurden
(d.h. sie sind nicht eingebettet in eine Funktion oder ähnliches).
Diese sind von überall im Python-Skript lesbar.

Auf der anderen Seite gibt es lokale Variablen. Das sind Variablen, die innerhalb einer Funktion
definiert wurden und daher nur innerhalb dieser "gesehen" werden.


Versuchen Sie, die folgenden Beispiele nachzuvollziehen.
    
```python
"""x existiert nur global"""
x = 1
def f():
    print(x)
f()
```

```python
"""x existiert nur lokal"""
def f():
    x = 5
f()
print(x)
```

```python
"""x existiert global und lokal"""
x = 1
def f():
    x = 5
    print(x)
f()
print(x)
```


```python
"""x existiert global. Existiert es lokal?"""
x = 1
def f():
    if False:
        x = 7
    print(x)
f()
```


## Rekursion

Eine rekursive Funktion ist eine Funktion, die sich selbst in ihrer Definition nochmals aufruft.
Bekanntestes Beispiel dafür ist vermutlich die Fakultätsfunktion.

\\(n! = n \cdot (n-1) \cdot (n-2) \cdot ... \cdot 1
      = n \cdot (n-1)!\\)

Die Fakultät einer natürlichen Zahl \\(n\\) kann gelöst werden, indem man das Produkt von \\(n\\)
mit \\(n - 1!\\) berechnet.

In Python-Code würde das ganze so aussehen:

```python
def fak(n):
    if n == 0:
        return 1
    return n * fak(n - 1)
```

Wichtig hierbei ist der Rekursionsanker (```if n == 0```), der dafür sorgt, dass die rekursiven
Aufrufe ab einem bestimmten Punkt stoppen.


### Kontostand

Schreiben Sie nun eine Funktion, die rekursiv einen Kontostand berechnet, der anfangs (\\(t = 0\\))
1000 € beträgt, und jährlich mit 5 % verzinst wird.

Beispiel:

```python  
print(kontostand(t=0))
```

Ausgabe:

```
1000
```

```python  
print(kontostand(t=1))
```

Ausgabe:

```
1050
```

usw.

### Zahlen von 1 bis n

Schreiben Sie eine Funktion, die bei Eingabe einer natürlichen Zahl n die Zahlen von 1 bis n ausgibt.
Jedoch ohne eine Schleife zu benutzen!

## Aufgabe Palindrom

Schreiben Sie eine Funktion *is_palindrom*, die überprüft, ob ein String ein Palindrom ist (also vorwärts und rückwärts gelesen das gleiche ergibt).


Beispiel:

```python
def is_palindrom(wort):
    ...

print(is_palindrom("anna"))
print(is_palindrom("anne"))
```

Ausgabe:

```
True
False
```

Sie können die Aufgabe sowohl iterativ als auch rekursiv lösen.

## Matrix Multiplikation

Schreiben Sie eine Funktion mat_mul(matrix_a, matrix_b), die zwei Matrizen als Eingabe nimmt und ihr 
Produkt ausgibt.

Hinweis:

Eine Matrix können Sie als Liste von Listen speichern:

```python
mat = [[1, 0, 0],
       [0, 1, 0],
       [0, 0, 1]]
```


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

Schreiben Sie eine Funktion, die für Wörter, die aus Kleinbuchstaben bestehen, die sogenannte _ROT13_ Verschlüsselung implementiert (also die Cäsar Verschlüsselung für n=13).

```python

def rot13(wort):
    ...


print(rot13("hallo welt"))
```

Ausgabe:

```
'unyyb jryg'
```
  
Hierfür ist es hilfreich, ein Dictionary zu erstellen, das jedem Buchstaben seinen "verschlüsselten" Buchstaben zuweist

Kleine Hilfe:
   
```python
alphabet = 'abcdefghijklmnopqrstuvwxyz'
```
    
Erstellen Sie nun daraus einen String alphabet_verschoben (Slicing hilft!), der mit dem 13. Buchstaben beginnt.

Sie können nun das Dictionary füllen:

```python

dict_verschlüsselt = {}

for buchstabe, buchstabe_verschlüsselt in zip(alphabet, alphabet_verschoben):
    dict_verschlüsselt[buchstabe] = buchstabe_verschlüsselt
```

* Wie sieht die Funktion aus, die verschlüsselten Text wieder entschlüsselt?

# Pascalsches Dreieck

![PascalschesDreieck](https://upload.wikimedia.org/wikipedia/commons/0/0d/PascalTriangleAnimated2.gif)

(Quelle: https://de.wikipedia.org/wiki/Pascalsches_Dreieck)

Das Pascalsche Dreieck ist ein Dreieck aus Zahlen. In jeder Zeile sind die erste und die letzte Zahl jeweils Einsen. Für die weiteren Zahlen gilt folgende rekursive Formel:
z(zeile, i) = z(zeile-1, i-1) + z(zeile-1, i).

So gilt beispielsweise für die Zahl 6 (vierte Zeile) im obigen Dreieck: sie steht in der 4.Zeile (bei Null anfangen zu zählen!) an zweiter Stelle, und ist die Summe aus der Zahl in der 3. Zeile an erster Stelle und der Zahl in der 3. Zeile an zweiter Stelle.

Schreiben Sie eine Funktion pascal_zeile, die für eine gegebene Zeilennummer die Einträge des Pascalschen Dreiecks ausgibt.
