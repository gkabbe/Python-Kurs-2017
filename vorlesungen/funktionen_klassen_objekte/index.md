<!-- 
.. title: 3 - Funktionen, Klassen und Objekte
.. slug: funktionen_klassen_objekte
.. date: 2017-05-11 00:00:00 UTC+01:00
.. tags: mathjax
.. category: 
.. link: 
.. description: 
.. type: text
-->

# Funktionen

Funktionen sind ein wichtiger Baustein eines Computerprogramms. Sie erlauben eine bessere Gliederung des Codes und erleichtern die Wiederverwendung von Code-Stücken.

## Grundlagen

Um eine Funktion zu erstellen wird das Keyword **def** benötigt, anschließend kommt der Funktionsname, und dahinter eine Klammer, in die die Funktionsargumente geschrieben werden (falls die Funktion welche benötigt).

```python
def quadrat(x):
    return x * x
```

In dem oberen Beispiel hat die Funktion einen Rückgabewert (gekennzeichnet durch das **return** Statement).
Das bedeutet, dass die Funktion beim Aufruf einen Wert zurückgibt.

Das muss aber auch nicht zwingend sein:
Die folgende Funktion _hello_world_ z.B. gibt nur "Hello World" aus, hat aber kein return Statement.

```python
def hello_world():
    print("Hello World")
```

Nachdem eine Funktion erstellt wurde, muss sie aufgerufen werden, damit überhaupt etwas passiert:

```python
def quadrat(x):
    return x * x

zahl = 12
quadrat_der_zahl = quadrat(zahl)
print(zahl, "zum Quadrat ist", quadrat_der_zahl)
```

Man kann den Funktionsargumenten Defaultwerte geben, die benutzt werden, falls die Funktion ohne Parameter aufgerufen wird:

```python
def summe(a=0, b=0, c=0):
    return a + b + c
    
print(summe())
```

Ausgabe:

```
0
```

Es ginge aber z.B. auch:

```python
summe(1, 2) # a und b werden auf 1 und 2 gesetzt, c hat den Defaultwert 0

summe(a=100) # a wird auf 100 gesetzt, b und c haben den Defaultwert 0

summe(3, c=99.912) # a wird auf 3 und c auf 99.912 gesetzt, b hat den Defaultwert 0
```

Darüberhinaus ist es möglich, eine Funktion zu schreiben, die beliebig viele Argumente akzeptiert:

```python
def summe(*args):
    total = 0
    for value in args:
        total += value
    return total


print(summe(1))
print(summe(1, 2, 3))
print(summe(1, 2, 3, 4, 5, 6, 7, 8, 9, 10))
```

Ausgabe:
```
1
6
55
```
Alle Argumente, die _summe_ übergeben werden, werden in einem Tupel namens _args_ gespeichert.
Über diesen können wir dann iterieren.

## Rekursive Funktionen

Rekursive Funktionen sind Funktionen, die ein Problem lösen, indem sie sich selbst nochmal (mit anderen Parametern) aufrufen.

Das bekannsteste Beispiel ist vermutlich die Fakultätsfunktion:
Wie die meisten vermutlich noch aus der Schulzeit (oder aus der Mathevorlesung) wissen, ist die Fakultät
einer natürlichen Zahl n definiert als:

\\(n! = n \cdot (n-1) \cdot (n-2) \cdot ... \cdot 1\\)

Obige Formel können wir aber auch folgendermaßen schreiben:

\\(n! = n \cdot (n-1)!\\)

In dieser Schreibweise sagt uns die Formel also, dass die Fakultät von n einfach n mal die Fakultät der Vorgängerzahl von n ist.

In Python übersetzt sieht die Formel so aus:

```python
def fakultät(n):
    return n * fakultät(n - 1)
```

Hier fehlt allerdings noch eine Kleinigkeit: wir brauchen einen Rekursionsanker, der uns sagt, wann wir aufhören können zu rechnen. 
Fehlt dieser Anker, wird die Funktion sich immer wieder selbst aufrufen, bis irgendwann folgende Fehlermeldung erscheint:

```
RecursionError: maximum recursion depth exceeded
```

Bei der Fakultät können wir ausnutzen, dass \\(0! = 1\\).

Als Programm geschrieben, sieht das ganze dann so aus:

```python
def fakultät(n):
    if n == 0:
        return 1
    else:
        return n * fakultät(n-1)
```

Hundertprozentig sicher ist diese Funktion allerdings noch nicht. 
Denn wenn \\(n < 0\\), findet die Funktion wieder kein Abbruchkriterium.


Hier könnte man nun noch mit einer weiteren if-Abfrage prüfen, ob \\(n < 0\\), und in dem Fall
z.B. ```None``` ausgeben.


