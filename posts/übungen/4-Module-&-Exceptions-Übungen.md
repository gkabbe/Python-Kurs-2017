<!-- 
.. title: 4 - Module & Exceptions - Übung
.. slug: module_exceptions_uebungen
.. date: 2018-11-10 00:00:00 UTC+01:00
.. tags: 
.. category: 
.. link: 
.. description: 
.. type: text
-->



# Module

## timeit

* Benutzen Sie die time-Funktion aus dem time-Modul, um die Laufzeit des Pascalschen Dreieck Programms zu bestimmen. 

* Schreiben Sie eine Wrapper-Funktion _timeit_, die die Laufzeit beliebiger Funktionen misst.

* Benutzen Sie sie als Decorator

## Lotto

* Spielen Sie Lotto! (aber nur am Computer...) Schreiben Sie ein Programm, das 6 Kugeln aus 49 zieht (dafür ist das random Modul sehr hilfreich).

* Schreiben Sie ein Programm, das eine Million mal Lotto spielt.

* Speichern Sie in einem Histogramm, wie oft das Programm null richtige, einen richtigen, ..., sechs richtige zieht. Benutzen Sie dafür die Klasse Counter aus dem Modul collections

## Type Checking

* Benutzen Sie das types-Modul, und schreiben Sie einen Decorator check_if_number, der prüft, ob alle Argumente einer Funktion vom Typ Integer oder Float sind. Falls nicht, soll ein ValueError auftreten

## Memoize

* Versuchen Sie, das Pascalsche Dreieck mit 40 Zeilen zu erzeugen

* Brechen Sie genervt nach 2 Minuten Wartezeit ab

Das Problem bei der momentanen Lösung ist, dass Zeilen die vorher schonmal berechnet wurden, immer wieder neu berechnet werden

* Schreiben Sie nun eine Wrapper-Funktion _memoize_, die eine andere Funktion f als Argument erwartet. Die memoize Funktion beinhaltet ein Dictionary d. 
Definieren Sie in der memoize Funktion eine weitere Funktion f_extended(x). Diese prüft, ob x schon in d enthalten ist. 
Wenn nicht, setzt sie d[x] auf f(x). Anschließend gibt sie den unter d[x] gespeicherten Wert zurück. Die memoize Funktion muss schließlich noch f_extended zurückgeben.
Benutzen Sie memoize als Decorator und versuchen Sie nochmals die Berechnung von 40 Zeilen des Pascalschen Dreiecks

Hinweis: tatsächlich gibt es diese Funktion schon in der Standardlibrary. Sie ist im Modul functools zu finden und heißt lru_cache

## rot-n

Schreiben Sie eine Funktion, die einen Parameter n annimmt und eine Funktion zurückgibt, die einen String per Cäsar-Code verschlüsselt. Der Parameter n legt dabei fest, um wieviel Buchstaben die Funktion die Buchstaben der Eingabewörter verschiebt
