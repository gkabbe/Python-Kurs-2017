<!-- 
.. title: 2.5 - Python Selbsthilfekurs
.. slug: 2.5-doityourself
.. date: 2017-04-21 00:00:00 UTC+01:00
.. tags: 
.. category: 
.. link: 
.. description: 
.. type: text
.. author: Gabriel Kabbe
-->

# Hilfe in IPython

IPython hat ein paar Extras eingebaut, die das Lernen von Python leichter machen.
Mithilfe von Tab kann man sich z.B. viele Dinge ergänzen lassen.

Beispiel:

```python
liste = ["a", "a", "b", "c"]
liste.
```

Wenn wir nach dem Punkt Tab drücken, bekommen wir angezeigt, welche Methoden 
(was eine Methode genau ist, wird später noch genauer erklärt) die Liste ausführen kann.

Eine dieser Methoden ist "count".
Ergänzen Sie nun count, und benutzen die help-Funktion:

```python
liste = ["a", "a", "b", "c"]
help(liste.count)
```

Wenn Sie nun Enter drücken, sollte folgendes erscheinen:

```
Help on built-in function count:

count(...) method of builtins.list instance
    L.count(value) -> integer -- return number of occurrences of value
```

Eine kleine Dokumentation, die uns sagt, was count eigentlich tut.

Gleich mal ausprobieren:

```python
print(["a", "a", "b", "c"].count("a"))
```

Ergebnis ist 2, denn "a" kommt zweimal in der Liste vor.

Mithilfe der help-Funktion kann man also leicht herausfinden, wozu etwas in Python gut ist.

Probieren Sie doch auch mal aus:

```python
help(list)
```

```python
help(print)
```


```python
help(help)
```


## Aufgaben:

* Schauen Sie, was für weitere Methoden es für Listen gibt, und probieren Sie sie aus!

* Was passiert bei Strings?
