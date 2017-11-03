<!-- 
.. title: 3.5 - Klassen - Übung
.. slug: klassen_uebung
.. date: 2017-11-10 00:00:00 UTC+01:00
.. tags: 
.. category: 
.. link: 
.. description: 
.. type: text
-->


# Klassen

Schreiben Sie eine Klasse Student mit folgenden Eigenschaften:

* Ein neues Studenten-Objekt wird erstellt, indem man dem Konstruktor (d.h. der __init__ Funktion Namen und Vornamen des Studenten übergibt:

```python
student = Student(name="Müller", vorname="Heinz")
```

* Die Klasse soll eine Objektvariable _noten_liste_ besitzen, die zu Beginn eine leere Liste ist, sowie eine Methode _neue_note_, die der _noten_liste_ eine neue Note hinzufügt

* Schreiben Sie eine Methode _durchschnitts_note_, die den Durchschnitt aller Noten in _noten_liste_ bildet
