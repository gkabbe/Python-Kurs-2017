<!-- 
.. title: 8 - Übungen - 1.12.17
.. slug: numpy_uebungen
.. date: 2018-11-29 00:00:00 UTC+01:00
.. tags: mathjax
.. category: 
.. link: 
.. description: 
.. type: text
-->


## Vektoriell rechnen

Gegeben sind zwei Arrays

```python
arr1 = np.array([1, 2, 3])
arr2 = np.array([5, 6, 7])
```





## Broadcasting

Gegeben sind die Positionen von 3 Atomen:

```python
import numpy as np

atoms = np.array([[0., 0., 0.],
                  [3., 3., 3.],
                  [2., 8., 7.]]
                 )
```

sowie ihre Massen:

```python
masses = np.array([1., 1., 5.])
```

* Verschieben Sie die Positionen aller 3 Atome um [1., 2., 3.]

* Berechnen Sie den Schwerpunkt der 3 Atome

## Selektives Ändern eines Arrays

Gegeben ist folgender Array:

```python
riddle = np.array([[ 533.,  502.,  530.,  591.,  552.,  563.,  508.,  581.,  570.,  557.,  510.,  303.,  355.,  389.,  306.,  598.,  540.,  526.,  585.,  599.,  505.,  547.,  569.,  566.,  580.,  564.,  531.,  573.],
       [ 512.,  522.,  540.,  510.,  541.,  544.,  521.,  567.,  324.,  388.,  384.,  495.,  457.,  469.,  485.,  300.,  426.,  410.,  584.,  545.,  518.,  591.,  518.,  536.,  508.,  556.,  595.,  560.],
       [ 545.,  584.,  521.,  552.,  589.,  583.,  314.,  301.,  461.,  473.,  436.,  469.,  478.,  440.,  449.,  431.,  461.,  461.,  322.,  319.,  592.,  522.,  554.,  569.,  593.,  502.,  551.,  514.],
       [ 576.,  517.,  538.,  588.,  550.,  331.,  529.,  532.,  470.,  469.,  471.,  461.,  426.,  400.,  450.,  462.,  422.,  430.,  454.,  487.,  398.,  529.,  584.,  567.,  594.,  522.,  530.,  506.],
       [ 542.,  582.,  520.,  525.,  319.,  575.,  543.,  481.,  413.,  474.,  408.,  446.,  433.,  465.,  409.,  448.,  407.,  401.,  485.,  434.,  403.,  360.,  525.,  523.,  581.,  528.,  555.,  567.],
       [ 533.,  588.,  569.,  383.,  581.,  541.,  558.,  448.,  411.,  425.,  403.,  463.,  423.,  457.,  493.,  472.,  460.,  470.,  444.,  418.,  498.,  426.,  340.,  577.,  556.,  544.,  560.,  589.],
       [ 576.,  552.,  550.,  365.,  587.,  543.,  575.,  586.,  425.,  430.,  493.,  488.,  446.,  460.,  447.,  493.,  404.,  414.,  444.,  430.,  417.,  449.,  317.,  538.,  559.,  596.,  513.,  553.],
       [ 567.,  574.,  374.,  513.,  578.,  593.,  539.,  555.,  512.,  407.,  435.,  483.,  458.,  456.,  462.,  433.,  497.,  465.,  459.,  400.,  445.,  436.,  456.,  356.,  547.,  526.,  508.,  573.],
       [ 537.,  515.,  398.,  576.,  525.,  530.,  529.,  584.,  544.,  513.,  450.,  420.,  426.,  489.,  441.,  432.,  427.,  444.,  482.,  415.,  486.,  472.,  466.,  320.,  501.,  535.,  592.,  580.],
       [ 539.,  542.,  304.,  522.,  565.,  500.,  559.,  530.,  554.,  520.,  526.,  594.,  423.,  472.,  477.,  468.,  428.,  374.,  343.,  332.,  379.,  419.,  477.,  354.,  557.,  554.,  554.,  550.],
       [ 544.,  383.,  567.,  520.,  575.,  372.,  393.,  528.,  546.,  571.,  531.,  538.,  548.,  540.,  566.,  355.,  387.,  407.,  471.,  332.,  352.,  347.,  369.,  494.,  394.,  566.,  590.,  521.],
       [ 590.,  326.,  524.,  327.,  357.,  501.,  559.,  348.,  566.,  516.,  522.,  505.,  502.,  501.,  363.,  445.,  442.,  398.,  329.,  548.,  591.,  512.,  595.,  358.,  344.,  571.,  519.,  543.],
       [ 571.,  362.,  322.,  544.,  251.,  223.,  523.,  544.,  355.,  542.,  597.,  587.,  571.,  322.,  446.,  377.,  343.,  108.,  509.,  573.,  136.,  584.,  672.,  367.,  349.,  564.,  543.,  520.],
       [ 585.,  312.,  225.,  228.,  435.,  484.,  215.,  536.,  336.,  522.,  529.,  557.,  375.,  455.,  350.,  371.,  108.,  523.,  507.,  218.,  298.,  221.,  292.,  244.,  242.,  294.,  556.,  573.],
       [ 552.,  232.,  444.,  458.,  454.,  435.,  234.,  564.,  503.,  365.,  589.,  555.,  303.,  394.,  582.,  364.,  507.,  258.,  299.,  258.,  219.,  291.,  269.,  269.,  243.,  230.,  281.,  536.],
       [ 279.,  522.,  453.,  406.,  419.,  487.,  444.,  514.,  283.,  398.,  521.,  352.,  487.,  309.,  347.,  108.,  214.,  236.,  602.,  261.,  221.,  200.,  292.,  235.,  261.,  236.,  292.,  540.],
       [ 227.,  460.,  430.,  405.,  451.,  108.,  544.,  454.,  409.,  379.,  505.,  595.,  314.,  317.,  325.,  108.,  236.,  279.,  270.,  234.,  226.,  553.,  215.,  219.,  246.,  622.,  540.,  577.],
       [ 595.,  218.,  209.,  456.,  108.,  584.,  549.,  576.,  450.,  401.,  491.,  515.,  321.,  654.,  697.,  267.,  276.,  249.,  531.,  651.,  606.,  558.,  604.,  693.,  594.,  570.,  560.,  523.],
       [ 524.,  564.,  433.,  400.,  108.,  516.,  575.,  413.,  662.,  648.,  666.,  470.,  579.,  488.,  641.,  210.,  204.,  553.,  541.,  648.,  238.,  656.,  230.,  642.,  549.,  599.,  598.,  500.],
       [ 524.,  596.,  549.,  439.,  108.,  108.,  437.,  691.,  693.,  671.,  659.,  628.,  420.,  494.,  581.,  282.,  246.,  506.,  611.,  612.,  227.,  670.,  275.,  691.,  634.,  461.,  597.,  553.],
       [ 573.,  577.,  595.,  436.,  468.,  108.,  479.,  679.,  686.,  686.,  678.,  627.,  435.,  586.,  515.,  297.,  264.,  263.,  679.,  648.,  521.,  570.,  609.,  601.,  687.,  481.,  574.,  509.],
       [ 501.,  544.,  508.,  539.,  430.,  499.,  108.,  474.,  656.,  669.,  601.,  462.,  108.,  108.,  108.,  502.,  232.,  685.,  687.,  201.,  437.,  569.,  549.,  576.,  558.,  409.,  516.,  584.],
       [ 527.,  515.,  584.,  581.,  505.,  411.,  462.,  489.,  465.,  454.,  406.,  108.,  108.,  347.,  307.,  262.,  576.,  580.,  282.,  262.,  240.,  295.,  276.,  210.,  214.,  280.,  277.,  509.],
       [ 537.,  562.,  565.,  573.,  559.,  500.,  466.,  464.,  410.,  404.,  108.,  108.,  108.,  108.,  108.,  287.,  543.,  521.,  686.,  659.,  261.,  278.,  266.,  276.,  293.,  288.,  554.,  541.],
       [ 586.,  596.,  509.,  579.,  530.,  508.,  579.,  480.,  439.,  629.,  631.,  458.,  488.,  416.,  429.,  477.,  487.,  535.,  564.,  546.,  538.,  529.,  596.,  412.,  500.,  559.,  508.,  596.],
       [ 536.,  578.,  502.,  522.,  531.,  525.,  587.,  580.,  501.,  487.,  439.,  432.,  478.,  443.,  405.,  548.,  533.,  439.,  486.,  415.,  476.,  417.,  472.,  541.,  528.,  595.,  531.,  549.],
       [ 548.,  562.,  550.,  561.,  584.,  598.,  572.,  584.,  581.,  544.,  577.,  591.,  548.,  530.,  512.,  552.,  587.,  511.,  577.,  565.,  591.,  560.,  565.,  595.,  544.,  556.,  585.,  520.]])
```

Wandeln Sie den Array folgendermaßen um:

* Zahlen zwischen 200 und 300 -> 0
* Zahlen zwischen 300 und 400 -> 40
* Zahlen zwischen 400 und 500 -> 156
* Zahlen zwischen 600 und 700 -> 220

Speichern Sie den Ergebnisarray als Bild

```python
from PIL import Image

Image.fromarray(riddle).save("solution.png")
```


## Inverse einer Matrix

* Schreiben Sie eine Funktion, die die Inverse einer 2x2 Matrix berechnet.

* Schreiben Sie eine Funktion, die die Adjunkte einer beliebigen (quadratischen) Matrix bestimmt

* Benutzen Sie die vorherige Funktion, um beliebige quadratische Matrizen zu invertieren

Hinweise:

* np.linalg.det berechnet die Determinante einer Matrix


## Apfel-Männchen

Gegeben ist eine rekursive Folge für komplexe Zahlen


\\(z_{i+1} = z_i^2 + c \\)

mit \\(z_0 = 0\\)

Je nachdem wie man c wählt, bleibt diese Folge beschränkt (d.h. der Betrag der komplexen Zahl (np.abs) bleibt unter einer gewissen Grenze), oder sie divergiert.

* Erstellen Sie einen komplexen 2D-Array c, der die komplexe Ebene darstellen soll. Der Realteil soll dabei von -2 bis 2 verlaufen, der Imaginärteil von -i bis i.
 Dies erreichen Sie durch folgende Schritte:
  * Erstellen Sie einen Float-Array für den Realteil und einen für den Imaginärteil:
    
```python
real = np.linspace(-2, 2, 100)
imag = np.linspace(-1, 1, 50) * 1j
```

  * Mit folgendem Befehl machen Sie aus dem imag Array einen Spaltenvektor:
    
```python
imag = imag[:, np.newaxis]
```

    Addieren Sie nun die beiden Vektoren, und Sie sollten einen zweidimensionalen Array erhalten, der Punkte der komplexen Ebene zwischen -2-1j und 2+2j enthält.

  * Erstellen Sie einen komplexen Array z, sowie einen Integer-Array counter, die beide die selbe shape wie c haben

  * Nun beginnt die Hauptschleife: berechnen Sie in 100 Schritten die Werte z_1 bis z_100, indem Sie ihren Array z immer wieder neu berechnen. Überprüfen Sie nach jeder Rechnung, welche Elemente des z-Arrays noch einen Betrag (np.abs) kleiner 10 haben (-> den resultierenden Boolschen Array können Sie zu counter hinzuaddieren. True wird dann als Wert 1, und False als Wert 0 aufgefasst).

  * Zum Schluss können Sie sich ein Bild des Counters ausgeben lassen. Dazu müssen Sie zu Beginn des Skripts folgendes Paket importieren:
    
```python
from PIL import Image
```

    anschließend können Sie mit folgenden 3 Zeilen ein Bild speichern:

```python
counter = np.array(counter/100. * 255, dtype=np.uint8)
img = Image.fromarray(counter)
img.save("mandelbrot.png") 
```

   * Experimentieren Sie auch mit anderen Grenzen des Arrays c. Sie können so weiter in das Apfelmännchen "zoomen".

    
## Monte Carlo

![PI_Berechnung](https://upload.wikimedia.org/wikipedia/commons/8/84/Pi_30K.gif)

Quelle: https://en.wikipedia.org/wiki/Monte_Carlo_method

Bestimmen Sie die Kreiszahl \\(\pi\\), indem Sie zufällig Punkte in einem Koordinatensystem der Länge 1 und Höhe 1 verteilen. 
Wenn Sie einen Kreis ziehen, dessen Zentrum im Ursprung des Koordinatensystems liegt, ist ein Viertel davon in dem Koordinatensystemausschnitt zu sehen.
Einige der zufällig gewählten Punkte werden nun innerhalb des Viertelkreises liegen, andere außerhalb. 
Bestimmen Sie über das Verhältnis \\(\frac{\text{Anzahl der Punkte im Kreis}}{\text{Gesamtanzahl der Punkte}}\\) die Zahl \\(\pi\\). 

Hinweis: 
Mittels

```python
np.random.random(shape)
```

können Sie einen Array mit Zufallszahlen im Intervall [0, 1) erzeugen.
