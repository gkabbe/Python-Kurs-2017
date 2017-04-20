<!-- 
.. title: 1 - Grundlagen: Übung
.. slug: 1-grundlagen-uebung
.. date: 2017-04-01 11:13:28 UTC+02:00
.. tags: 
.. category: 
.. link: 
.. description: 
.. type: text
.. author: Gabriel Kabbe
-->

Schreibe hier deinen Eintrag hin.
## Mit dem Python Interpreter spielen

  * Machen Sie sich mit dem Python Interpreter vertraut. 
    * Führen Sie ein paar Rechenaufgaben durch
    * Benutzen Sie den print-Befehl, um beliebigen Text in der Kommandozeile auszugeben

## Hello World

* Schreiben Sie das Hello World Programm in einer Datei hello_world.py und führen Sie es mit dem Befehl
    
```
python hello_world.py
```
  
  aus.

* Schreiben Sie das Hello World Programm so um, dass es eine Datei _hello_world_ öffnet, und in diese "Hello World!" schreibt.

* Schreiben Sie ein Programm, das ihre neu erstellte Datei _hello_world_ wieder ausliest!

* Schreiben Sie ein Programm, das die Datei _hello_world_ öffnet und eine weitere Zeile "How are you?" anhängt. 

* Schreiben Sie ein interaktives "Hello User"-Programm! Beim Start soll es den Benutzer nach seinem Namen fragen, und ihn anschließend mit seinem Namen grüßen.

## Datentypen

* Erstellen Sie eine Variable mit dem Namen _var1_, die den Wert 10 enthält
* Nun erstellen Sie eine Variable _var2_, die den String ":-)" enthält
* Welchen Datentyp hat die Variable _var3_, die folgendermaßen erstellt wird: 
    
```python
var3 = var1 * var2

```

* Erhöhen Sie den Wert der Variablen _var1_ um 0.3. Welchen Datentyp hat sie jetzt?
* Addieren Sie nun eine komplexe Zahl hinzu. Wie ändert sich der Datentyp?

## Casten von Datentypen

In manchen Fällen ist es sinnvoll, von einem gegebenen Datentyp zu einem anderen zu wechseln.
Z.B. lässt sich ein Integer folgendermaßen zu einem Float konvertieren:

```python
x = 3
x_float = float(x)
```

Konvertieren Sie nun:

* float -> int
* float -> complex
* float -> str
* str -> int
* str -> float
* str -> complex

usw.

Schreiben Sie nun eine for-Schleife, in der die Zahlen 0.0, 0.1, ..., 0.9 ausgegeben werden

## Boolesche Variablen
  
Gegeben seien die Variablen

```python
student_motiviert = True
student_ausgeschlafen = False
unterricht_spannend = True
```

* Welchen Wert hat 

```python
lernerfolg = student_ausgeschlafen or (student_motiviert and unterricht_spannend)
```

* Was passiert bei folgender Klammernsetzung?

```python
lernerfolg = (student_ausgeschlafen or student_motiviert) and unterricht_spannend
```

* Wir setzen unterricht_spannend nun auf den (rein hypothetischen) Wert False. Wie ändert sich der Lernerfolg in den beiden oben genannten Fällen?


## Passwortabfrage

Schreiben Sie ein passwortgeschütztes Hello World Programm.

* Beim Start fragt es nach einem Passwort. Erst wenn der User das korrekte Passwort eingegeben hat, wird "Hello World" ausgegeben.

* Diesmal sind nur 3 Fehlversuche erlaubt. Danach bricht das Programm ohne Ausgabe ab
