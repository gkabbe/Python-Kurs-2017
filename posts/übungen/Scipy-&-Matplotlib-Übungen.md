<!--
.. title: 8 - Scipy & Matplotlib - Übungen
.. slug: scipy_matplotlib
.. date: 2018-01-11 00:00:00 UTC+01:00
.. tags: mathjax
.. category:
.. link:
.. description:
.. type: text
-->

Viele Beispiele zu Matplotlib finden Sie auch [hier](http://matplotlib.org/gallery.html).


# 1-Dimensionale Plots

Plotten Sie

# 2-Dimensionale Histogramme

* Erzeugen Sie mithilfe von Numpy normalverteilte Punkte im zweidimensionalen Raum.
  Die Punkteverteilung soll ihr Zentrum bei (130, 270) haben und eine Standardabweichung von 10 in x-Richtung, und von 50 in y-Richtung

* Benutzen Sie dazu

```python
import matplotlib.pyplot as plt
import numpy as np


x = np.random.normal(loc=..., scale=..., size=...)
y = ...

plt.hist2d(...)
```

# Mehrdimensionale Funktionen plotten

Gegeben sei eine Funktion f(x, y), z.B.


\\(f(x, y) = exp(-x^2) * sin(y)\\)

* Schreiben Sie die Funktion \\(f\\) Numpy-kompatibel in Python

* Kreieren Sie nun einen Array mit den x-Koordinaten und y-Koordinaten, an denen \\(f\\) ausgewertet werden soll.
  Hierfür bietet sich np.linspace(start, end, length) an.

* Um aus den zwei eindimensionalen Arrays ein zweidimensionales Gitter zu machen, benutzen Sie

```python
X, Y = np.meshgrid(x, y)
```

  Wenn x die Länge len_x, und y die Länge len_y hat, erzeugt np.meshgrid zwei 2D-Arrays der shape (len_y, len_x).
  Jeder Eintrag der Arrays entspricht einem Punkt auf dem Gitter, was durch x und y aufgespannt wird.
  X enthält alle x-Werte auf der jeweiligen Gitter-Position, Y die entsprechenden y-Werte.

* Werten Sie nun Z = f(X, Y) aus.

  Mittels

```python
plt.pcolormesh(X, Y, Z)
plt.show()
```

  können Sie f(X, Y) zweidimensional grafisch darstellen.



# Güte eines Fits

Haben wir eine Funktion an unsere Messdaten gefittet, ist die nächste wichtige Frage, die wir uns stellen müssen, wie gut unsere Fit-Funktion eigentlich die Daten beschreibt.

## Bestimmtheitsmaß

Das [Bestimmheitsmaß](https://de.wikipedia.org/wiki/Bestimmtheitsma%C3%9F) ist definiert als:

R² = 1 - (Summe der quadratischen Abweichungen des Fits von den Messwerten) / (Varianz der Messwerte)

Falls der Fit keine Abweichung von den Messwerten zeigt, ist R² = 1.
Im anderen Extremfall ist die Abweichung des Fits von den Messwerten so groß wie die Varianz der Messwerte selbst. In diesem Fall besteht kein linearer Zusammenhang und R² = 0.

* Gegeben seien

```python
x = np.linspace(0, 10, 51)
y = np.array([  0.52691411,   0.15337663,   1.43856168,   2.40676542,
                3.39139498,   3.45232301,   4.37507344,   3.42645346,
                4.04379333,   5.39198639,   6.99364368,   7.50859895,
                7.69962232,   8.30130309,   8.27225713,   9.15863628,
                9.39810611,  11.0523773 ,  10.46304528,  12.20255932,
               11.70786975,  12.23490009,  13.2744774 ,  14.46828046,
               14.67572454,  15.88850194,  15.03465002,  16.63086629,
               16.35790349,  17.79372946,  18.81870178,  18.53822878,
               19.42759411,  20.00532161,  21.03680116,  20.0965816 ,
               21.61260744,  21.63133823,  22.8952802 ,  24.07572217,
               23.94384869,  24.94396931,  25.81434391,  26.41242246,
               25.413351  ,  27.44888064,  28.09184088,  27.54036923,
               29.35779925,  28.6853119 ,  29.61227889])
```

  Fitten Sie eine lineare Funktion an die Messdaten und bestimmen Sie R².

* Wiederholen Sie das Prozedere für

```python
y = np.array([ 0.90295774,  0.13220468, -0.01083773, -0.71269602,  1.20154739,
              -1.14519411,  0.62495417,  0.58180219,  0.91674602, -0.99448903,
              -0.64488626, -0.15963476, -0.11970351, -0.74662734,  0.44611458,
               0.47010857,  1.0741637 ,  0.07617371,  0.66626109, -0.31254391,
               1.19615032, -0.21362221, -0.94589967, -1.32260225, -1.17339299,
              -1.89316188, -0.49097431, -1.17783081,  1.01988436,  1.12720555,
              -0.76142478, -0.49120147,  1.95458002,  1.17177714, -1.41571477,
               0.59663724, -1.0334638 , -0.46439517,  0.00567392, -0.87581851,
               0.65681717, -0.65358466,  2.25401457, -0.12853615, -0.10993498,
               1.11431949, -0.78214815, -1.33849923,  1.44143436,  1.5750663 ,
               1.06671372])
```
