<!-- 
.. title: 2 - Übungen - 27.10.17
.. slug: 2-datenstrukturen-ubungen
.. date: 2017-10-27 14:19:07 UTC+02:00
.. tags: mathjax
.. category: 
.. link: 
.. description: 
.. type: text
-->


# Listen

## Quadratzahlen korrigieren  
Gegeben sei folgende Liste:

```python
quadrat_zahlen = [1, 4, 9, 16, 26, 36, 49, 64, 81, 100]
```

* Finden Sie die fehlerhafte Quadratzahl und ersetzen Sie sie mit der korrekten Zahl.

* Fügen Sie noch eine weitere Quadratzahl hinzu



## Noch mehr Listen

* Gegeben ist eine Liste von Strings

```python
string_liste = ["1", "2", "3", "4", "5", "6", "7", "8", "9", "10"]
```

  Machen Sie daraus eine Liste von Integers!


## Listen entpacken

Gegeben ist eine Liste von zwei Elementen


```python
liste = ["erstes element", "zweites element"]
```

Was passiert wenn Sie folgendes schreiben:

```python
a, b = liste
```

Funktioniert das auch für mehr Elemente?


## Liste von Listen

Gegeben ist

```python
liste = [[0, "a"], [1, "b"], [2, "c"]]
```

Iterieren Sie nun mit einer for-Schleife über die Liste:

```python
for x in liste:
    ...
```

Was steht nun in x?

Entpacken Sie x, sodass Sie eine Variable i und eine Variable elem haben.
Was enthält nun i, und was elem?

Entpacken Sie nun direkt in der Zeile der for-Schleife:

```python
for i, elem in liste:
    ...
```


## Enumerate

Sie haben eine Liste

```python
liste = ["a", "b", "c"]
```

Wenden Sie die Funktion enumerate darauf an:

```python
enum = enumerate(liste)
```

Um sich anzuschauen, was enum enthält, schreiben Sie:

```python
print(list(enum))
```

Benutzen Sie nun enumerate, um parallel über den Index und die Elemente einer Liste zu iterieren.


## zip

Diesmal haben Sie zwei Listen:


```python
erste_liste = ["a", "b", "c"]
zweite_liste = ["x", "y", "z"]
```

Benutzen Sie zip (Reißverschluss):

```python
gezippte_liste = zip(erste_liste, zweite_liste)
print(list(gezippte_liste))
```

Was ist passiert?


Nutzen Sie nun zip, um über folgende drei Listen zu iterieren:

```python
liste1 = ["S", "i", "e", "ri"]
liste2 = ["o", "s", "s", "ch"]
liste3 = ["", "t", "", "tig"]
```

Lassen Sie sich in jedem Schleifendurchlauf die Summe der Elemente ausgeben mit print.


## Einkaufliste:

* Erstellen Sie eine Einkaufsliste bestehend aus (maximal) 10 Produkten, sowie eine Liste mit den dazugehörigen Preisen.
  
  Oder benutzen Sie die hier:
        
```python
einkaufs_liste = ["apfel", "milch", "banane", "joghurt", "käse"]
preise = [0.40, 0.59, 0.30, 1.20, 2.30]
```
      
* Iterieren Sie mithilfe einer for-Schleife über alle Elemente in _einkaufs_liste_

* Benutzen Sie enumerate, um die Elemente in _einkaufs_liste_ durchzuzählen

* Iterieren Sie nun über Gegenstand und Preis, so dass Sie als Ausgabe bekommen:

```
Gegenstand_1, Preis_1
Gegenstand_2, Preis_2
...
Gegenstand_10, Preis_10
```

(Hinweis: zip!)

* Lassen Sie sich nun nur jeden zweiten Gegenstand ausgeben

# Daten einlesen:

* Schreiben Sie eine Datei "Daten", in die Sie ein paar numerische Werte eintragen (am einfachsten ist es, wenn Sie pro Zeile einen Wert schreiben)

* Schreiben Sie nun ein Programm, das die Datei "Daten" öffnet und die Zahlen in einer Liste speichert

* Berechnen Sie die Summe und den Mittelwert der Daten
  

# Strings


* Schreiben Sie ein Programm, das den User nach Input fragt, und das Geschriebene in Großbuchstaben
zurückgibt. Bei Eingabe von "Hallo" sollte also "HALLO" ausgegeben werden


* Finden Sie heraus, wie man aus einem String eine Liste von Strings erstellt

  z.B: "Dies ist ein Satz" -> ["Dies", "ist", "ein", "Satz"]

* Schreiben Sie ein Programm, das den User nach einem Satz fragt, und nur das erste und das letzte
  Wort zurückgibt

* Finden Sie heraus, wie man die Reihenfolge der Elemente in einer Liste umdreht

* Schreiben Sie ein Programm, das den User nach einem Satz fragt, und die Wörter in umgekehrter
  Reihenfolge ausgibt

# Mengen (Sets)

## Einkäufe

Sie und ein(e) Bekannte(r) waren shoppen. 
Sie haben gekauft:

```python
meine_einkäufe = {"hose", "jacke", "schuhe", "schokoriegel", "schal", "flatscreen"}
```

Ihr Bekannter hat gekauft:

```python
seine_einkäufe = {"buch", "schuhe", "mütze", "jacke", "softdrink"}
```

Benutzen Sie Mengenoperationen um herauszufinden:

* Was ist die Gesamtmenge, die Sie beide eingekauft haben?

* Was hat Ihr Bekannter gekauft, was Sie auch gekauft haben?

* Was hat Ihr Bekannter gekauft, das Sie nicht gekauft haben?

* Was haben Sie gekauft, das Ihr Bekannter nicht gekauft hat?

* Welche Dinge haben Sie nicht beide gekauft?


## Buchstaben in einem Wort

Benutzen Sie set, um herauszufinden, aus wieviel verschiedenen Buchstaben ein Wort besteht


## Sieb des Eratosthenes

Das Sieb des Eratosthenes ist ein Algorithmus, mit dem man Primzahlen bestimmen kann.
Er lässt sich in Python gut mit Mengen lösen.

Um die Primzahlen von 2 bis _n_max_ zu bestimmen, tun Sie folgendes:

* Erstellen Sie eine Menge _numbers_ der Zahlen von 2 bis _n_max_

* Erstellen Sie eine Variable _next_prime_ = 2

* Solange _next_prime_ < _n_max_/2 ist (while-Schleife!), erstellen Sie eine weitere Menge _not_prime_, die alle Vielfachen von _next_prime_ enthält. 
  Ziehen Sie diese von _numbers_ ab. Erhöhen Sie anschließend _next_prime_ um 1

* Wenn die while-Schleife beendet, sollten sich in _numbers_ nur noch die Primzahlen zwischen 2 und _n_max_ befinden




# Schere, Stein, Papier

Schreiben Sie ein Programm, das mit Ihnen Schere, Stein, Papier spielt.
Um den Computer dazu zu bringen, zufällig zwischen Schere, Stein und Papier zu wählen,
schreiben Sie folgendes:


```python
import random


computer_hand = random.choice(["Schere", "Stein", "Papier"])
```

Mit diesem Befehl wählt der Computer zufällig ein Element aus der Liste.


# Galgenmännchen

Schreiben Sie ein Programm, in dem ein String mit dem Namen _unbekanntes_wort_ gespeichert ist, sowie eine leere Menge mit dem Namen geratene_woerter.
In einer ewigen while-Schleife (while True) soll nun folgendes geschehen:

* Zuerst wird jeder Buchstabe von _unbekanntes_wort_ durchlaufen, und, wenn er in _geratene_woerter_ enthalten ist, ausgegeben. Ist er nicht enthalten, wird ein "-" ausgegeben.   
  Beispiel:  

    * Das geheime Wort ist _wochenende_
    * _geratene_woerter_ enthält {"n", "e"}
    * Ausgabe ist dann: "- - - - e n e n - e"

* Dann muss der User einen neuen Buchstaben eingeben (Achtung, genau einen!). Dieser wird in _geratene_woerter_ gespeichert

* Ergänzen Sie das Programm nun so, dass es mit einer Glückwunschsnachricht abbricht, sobald der User alle Buchstaben geraten hat.

* Erlauben Sie nur maximal 11 Fehlversuche, bevor das Programm mit "Game Over" abbricht

* Bonus: Anstatt das Wort in den Quellcode zu schreiben, lassen Sie es einen Mitspieler am Anfang eingeben. Wenn Sie
  folgendes zu Beginn schreiben:
  
```python
from getpass import getpass
```

können Sie mittels 
  
```python
unbekanntes_wort = getpass("Bitte zu ratendes Wort eingeben\n")
```

das geheime Wort eingeben lassen, ohne dass es auf dem Bildschirm zu sehen ist.
  
* Spielen Sie eine Runde Galgenmännchen mit Ihrem Nachbarn  


# Wortzähler

Schreiben Sie folgendes Python Programm:

```python
import this
```

Speichern Sie den resultierenden Text in einer extra Datei.

Analysieren Sie den Text, indem Sie ein Programm schreiben, das die Häufigkeit jedes Wortes im obigen Text zählt.
  
Hilfestellungen:

* Speichern Sie den Text entweder als String mit 3 Anführungszeichen am Anfang und am Ende (dann kann er sich auch über mehrere Zeilen erstrecken), oder lesen Sie ihn aus einer Datei aus, in die Sie ihn vorher geschrieben haben.

  Beispiel:
  
```python
text = """
Hier kann beliebiger Text
stehen, der sich über mehrere Zeilen erstreckt
"""
```

* Angenommen, Sie haben den gesamten Text in der Variablen _text_ gespeichert. Dann können Sie mit 
 
```python
wortliste = text.split()
```
  eine Liste der einzelnen Wörter erstellen.

* Um ungewünschte Zeichen aus dem Text zu entfernen, benutzen Sie:

```python
text.replace(zu_ersetzendes_zeichen, "")
```

* Zum Zählen der Wörter ist ein Dictionary sehr hilfreich! 

* Schreiben Sie das Programm nun so um, dass es die Häufigkeit der einzelnen Buchstaben zählt.

* Benutzen Sie Sets (Mengen), um herauszufinden, welche Wörter in jeder der ersten 6 Zeilen vorkommen.

* Erstellen Sie mithilfe von Sets eine Liste aller Buchstaben, die in dem Text vorkommen
