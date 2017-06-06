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


# Klassen und Objekte

Aus Zeitgründen wird dieses Thema nur kurz angeschnitten werden, auch wenn man eigentlich sehr viel mehr Zeit damit verbringen könnte.

Wir hatten zuvor gesehen, dass wir mit Funktionen gewissermaßen unseren Code etwas aufräumen können. 
Code der häufiger verwendet wird, wird als Funktion definiert, und später nur noch über den Funktionsnamen aufgerufen.

Ebenso können wir nun Variablen __und__ Funktionen zusammenfassen. Das geht über ein Objekt.
Die Klasse ist dabei die Blaupause, aus der ein Objekt erstellt wird. Aus einer Klasse können beliebig viele Objekte erstellt werden.

Eine Klasse wird typischerweise folgendermaßen in Python definiert (die "..." sollen nur andeuten, dass hier noch mehr Code stehen kann):

```python
class MeineKlasse:
    ...
    # Die __init__ Methode wird automatisch aufgerufen wenn ein Objekt aus einer Klasse erzeugt wird
    # Hier werden die Attribute des Objekts gespeichert
    def __init__(self, p1, p2, p3, ...):
        self.p1 = p1
        self.p2 = p2
        ...
        
    # Eine Methode ist wie eine Funktion, die aber auch noch auf die Attribute eines Objekts
    # Zugriff hat.
    # Wichtig ist, dass eine Methode als erstes Argument immer das entsprechende Objekt
    # bekommt 
    def methode1(self, q1, q2, ...)
        ...
    def methode2(self, ...)
        ...
    ...
```

_var1_ und _var2_ sind hier Objektvariablen, _methode1_ und _methode2_ Methoden, d.h. Funktionen, die jedes Objekt dieser Klasse besitzen wird.  
Die Methode *\_\_init\_\_* ist eine besondere Methode. Sie wird beim Erstellen eines Objekts aufgerufen.

## Minimales Beispiel

Eine ganz einfache Klasse könnte so aussehen:

```python
class Minimal:
    pass
```

_pass_ ist nur ein Platzhalter, der gar nichts macht. 
Dennoch reicht das schon, um eine funktionierende Klasse zu erstellen.
Wir können daraus nun ein Objekt erzeugen.

```python
mini = Minimal()
print(type(mini))
```

Dieses Objekt hat weder Methoden, noch Attribute.
Wir können in ihm jedoch nachträglich noch Attribute speichern:

```python
mini.mein_attribut = 5
print(mini.mein_attribut)
```

Damit funktioniert unsere Minmal-Klasse nun ähnlich wie ein Dictionary.
Der Unterschied ist bloß, dass wir statt mini["mein_attribut"] mini.mein_attribut schreiben.


## Beispiel mit einem Attribut

Da es unpraktisch ist, einem Objekt nach Erzeugung erst noch manuell die Attribute zuweisen zu müssen, benutzen wir diesmal die \_\_init\_\_ Methode.

```python
class Simple:
    def __init__(self):
        self.mein_attribut = 5

simple = Simple()
print(simple.mein_attribut)
```

Jedes Objekt, das nun erzeugt wird, speichert das Attribut _mein_atribut_ mit dem Wert 5.
Möchten wir das Attribut bei Erzeugung selbst festlegen, können wir es als Parameter in der \_\_init\_\_ Methode angeben:

```python
class MitAttribut:
    def __init__(self, attribut):
        self.mein_attribut = attribut

# Jetzt können wir Objekte mit unterschiedlichen Attribut-Werten erzeugen:
m_1 = MitAttribut(5)
m_2 = MitAttribut("hallo")
m_3 = MitAttribut([1, 2, 3])

print(m_1.mein_attribut)
print(m_2.mein_attribut)
print(m_3.mein_attribut)
```

## Praktisches Beispiel (für Physiker)

Ein Beispiel aus der Physik: wir wollen ein freies Teilchen in zwei Dimensionen simulieren, das durch den Raum fliegt. Wir können es über Position und Geschwindigkeit beschreiben. Darüberhinaus wollen wir ihm eine _move_ Methode geben, die als Parameter einen Zeitschritt akzeptiert, und das Teilchen in dieser Zeit weiterbewegt.

```python
class Particle:
    def __init__(self, x, y, v_x, v_y):
        self.x, self.y = x, y # hier wird die x, y Position des Teilchens festgelegt
        self.v_x, self.v_y = v_x, v_y # hier wird die Geschwindigkeit festgelegt
    def move(self, delta_t):
        self.x += self.v_x * delta_t # Teilchen wird in x-Richtung bewegt
        self.y += self.v_y * delta_t # Teilchen wird in y-Richtung bewegt
```

Wann immer wir auf eine Objektvariable zugreifen möchten, müssen wir dies mit einem vorangestellten _self._ kenntlich machen. 

Wir können nun folgendermaßen ein Objekt erstellen:

```python
mein_teilchen = Particle(0, 0, 1, 3)  # die Parameter, die wir hier angeben, werden an die __init__ Funktion weitergereicht
print(mein_teilchen.x, mein_teilchen.y)
for i in range(10):
    mein_teilchen.move(0.1)  # ruft die move Methode mit delta_t = 0.1 auf
    print(mein_teilchen.x, mein_teilchen.y)
```

In der ersten Zeile haben wir nun ein Objekt der Klasse _Particle_ erstellt und es _mein_teilchen_ genannt. Wir können nun auf die Methoden und Objektvariablen unseres Objekts zugreifen, indem wir hinter dem Objektnamen einen Punkt und dann den Objektvariablennamen bzw. Methodennamen schreiben.  
Es ist so sogar möglich, neue Objektvariablen auf diese Weise hinzuzufügen nachdem das Objekt schon erstellt wurde.

## Funktionen als Objekte

Diese Tatsache, mag etwas verwunderlich erscheinen, aber tatsächlich sind in Python auch Funktionen Objekte.
Das bedeutet, wir können mit ihnen alles machen, was wir auch mit anderen Objekten machen können.

Z.B können wir sie in einer Liste speichern:

```python
def x_hoch_2(x):
    return x * x


def x_hoch_3(x):
    return x * x * x


def x_hoch_4(x):
    return x * x * x * x


liste_mit_funktionen = [x_hoch_2, x_hoch_3, x_hoch_4]

for func in liste_mit_funktionen:
    print(func(5))
```

Oder wir können eine Funktion schreiben, die eine andere Funktion als Argument bekommt, und diese dann aufruft:

```python
def werte_funktionen_aus(irgendeine_funktion):
    for i in range(10):
        print(irgendeine_funktion(i))

werte_funktionen_aus(x_hoch_2)
```

Dieser Code würde also die Funktion _x_hoch_2_ auswerten an den Stellen 0 bis 9.

Andersherum können wir aber auch Funktionen definieren, die wiederum Funktionen zurückgeben:

```python
def gib_mir_eine_fkt(name):
    # Die Funktionen quadrat und hello_world werden hier innerhalb der Funktion gib_mir_eine_fkt
    # definiert, und sind daher nicht von außerhalb erreichbar
    def quadrat(x):
        return x * x
    def hello_world():
        print("Hello World!")

    if name == "quadrat":
        return quadrat
    elif name == "hello_world":
        return hello_world
    else:
        print("Unbekannter Funktionsname", name)

func1 = gib_mir_eine_fkt("quadrat")
print(type(func1))
# Über das Attribut __name__ können wir den Namen def Funktion sehen
print("Name der Funktion:", func1.__name__)
print(func1(5))

func2 = gib_mir_eine_fkt("hello_world")
print("Name der Funktion:", func2.__name__)
print(type(func2))
func2()

```

Ein praktisches Beispiel dafür wäre z.B. eine Funktion, die Polynom-Funktionen beliebigen Grades
erstellen kann:

```python
def polynom_creator(degree):
    def polynom(x):
        total = 0
        # Das ist die entscheidende Zeile:
        # Die range ändert sich, je nachdem welchen Wert der Parameter degree von polynom_creator
        # annimmt
        for n in range(0, degree + 1):
            total += x**n
        return total
    return polynom # hier wird das Funktionsobjekt zurückgegeben
```

Diese Funktion gibt uns ein Polynom der Form

\\(p(x) = x^n + x^{n-1} + ... + x^0\\)

zurück.

```python
polynom_zweiten_grades = polynom_creator(2) # hier erstellen wir ein Polynom zweiten Grades
polynom_dritten_grades = polynom_creator(3) # und hier eins dritten Grades
print(polynom_zweiten_grades(5))
print(polynom_dritten_grades(5))
```

Ausgabe:

```
31
156
```

### Grundlegende Verständnisfragen:

* Was für einen Datentyp gibt die Funktion _polynom_creator_ zurück?
* Was gibt die Funktion _polynom_ zurück?

## Scope -- Der Geltungsbereich von Variablen

Was passiert in folgendem Beispiel?

```python
x = 0

def f():
    x = 7
    print("x wurde gesetzt auf", x)

print("vor Ausführung von f: x =", x)
f()
print("nach Ausführung von f: x =", x)
```

Es sieht so aus, als würde die Funktion f unsere zuvor deklarierte Variable x ändern.
Tatsächlich ist die Ausgabe aber 

```
vor Ausführung von f: x = 0
x wurde gesetzt auf 7
nach Ausführung von f: x = 0
```

Der Grund für dieses Verhalten ist, dass Python dafür sorgt, dass Funktionen nicht aus Versehen globale Variablen (d.h. Variablen, die auf oberster Ebene definiert wurden) ändert.
Damit die globale Variable x nicht überschrieben wird, legt Python eine weitere Variable x an, die nur innerhalb der Funktion f Gültigkeit hat. Nach Verlassen der Funktion existiert diese nicht mehr, und es existiert nur noch das globale x.


Ein anderes Beispiel:

```python
x = 0

def f():
    print("x hat den Wert:", x)

f()
```

In diesem Beispiel haben wir innerhalb von f keine Variable x definiert. Dennoch funktioniert der Code. Python merkt in diesem Fall nämlich, dass keine lokale Variable x existiert und schaut deshalb nach, ob es eine globale Variable gibt.


Aber Vorsicht: sobald irgendwo in der Funktion auch eine Variable x auftaucht, existiert diese lokal, und Python wird nicht mehr im globalen Scope nach x suchen:

```python
x = 0

def f():
    if False:
        x = 7
    print("x hat den Wert:", x)

f()
```

Obwohl der Code nach der if-Bedingung niemals ausgeführt wird, sorgt er dafür, dass x nun lokal existiert.
Allerdings wird dem lokalen x nie ein Wert zugewiesen, weshalb das obige Beispiel mit einer Fehlermeldung endet.

## Funktions-Wrapper

Dass wir Funktionen wie Objekte anderen Funktionen übergeben dürfen, eröffnet uns nun ganz neue Möglichkeiten.
So können wir nun eine Funktion schreiben, die eine andere Funktion als Argument nimmt und daraus eine neue Funktion macht!

Beispiel:

```python
def wrapper(f):
    def f_enhanced():
        print("Am Anfang...")
        f()
        print("und am Ende passiert was neues!")
    return f_enhanced

def f():
    print("Hallo Welt")

f()
f_neu = wrapper(f)
f_neu()
```

Die Funktion _wrapper_ nimmt also eine Funktion, und macht daraus eine neue Funktion mit erweiterter Funktionalität. Natürlich hätten wir im obigen Beispiel auch einfach die Funktion _f_ umschreiben können, allerdings wird das spätestens dann anstrengend, wenn wir das für mehrere Funktionen machen wollen.

Ein weiteres Beispiel wäre z.B. ein wrapper, der Funktionen dahingehend erweitert, dass sie ihre Argumente auf bestimmte Kriterien prüfen:

```python
def check_args_nonnegative(f):
    def f_enhanced(*args):
        for arg in args:
            if arg < 0:
                raise ValueError("Bitte nur Argumente größer Null eingeben!") 
        return f(*args)
    return f_enhanced
```

Zu diesem Beispiel sind noch ein paar Worte zu sagen: wir sehen zum einen, dass f_enhanced mit *args als Argument definiert wurde. D.h. sie nimmt beliebig viele Argumente. Das ist notwendig, da f_enhanced ja mit vielen verschiedenen Funktionen soll, die unterschiedlich viele Funktionsargumente erwarten.

Bevor nun die ursprüngliche Funktion _f_ aufgerufen wird, wird zuerst geprüft, ob eines der gegebenen Argumente kleiner Null ist. In diesem Fall wird ein Fehler ausgelöst und die Funktion beendet sich.

Diesen 'Wrapper' können wir jetzt beispielsweise auf unsere Fakultätsfunktion anwenden:

```python
fak = check_args_nonnegative(fak) # wir speichern die neue Funktion wieder unter dem selben Namen
fak(5) # ok
fak(3) # ok
fak(0) # ok 
fak(-1) # ValueError!
```

Alternativ können wir anstelle von 'fak = check_args_nonnegative(fak)' auch einen sogenannten Decorator verwenden. Diesen müssen wir direkt über die Funktionsdefinition schreiben:

```python
@check_args_nonnegative
def fak(n):
    if n == 0:
        return 1
    else:
        return n * fak(n-1)
```

Die Funktion _fak_ hat dann automatisch die erweiterte Funktionalität.

