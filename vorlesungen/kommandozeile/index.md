<!-- 
.. title: 0 - Die Kommandozeile in Linux
.. slug: kommandozeile
.. date: 2017-03-06 20:03:02 UTC+01:00
.. tags: 
.. category: 
.. link: 
.. description: 
.. type: text
-->

# Die Kommandozeile #

Da wir in diesem Kurs auf einem Linux-Rechner arbeiten, kommen wir nicht darum herum, uns ein wenig mit Linux auseinanderzusetzen. 

Alle Befehle, die wir dem Computer mitteilen werden, werden über die sogenannte Kommandozeile ausgeführt.

Um sie zu öffnen, klicken wir auf das Startmenü und suchen nach "Terminal". Wenn wir den Eintrag mit der Maus anklicken, sollte sich ein Fenster öffnen. Das ist unsere Kommandozeile.

Nun können wir dem Computer ein paar einfache Befehle geben.

Schreiben wir

```bash
echo Hallo Welt
```

so sollte der Computer uns 

```bash
Hallo Welt
```

ausgeben.

# Dateien und Ordner #

Das Linux-Dateisystem besteht aus Dateien und Ordnern. Ganz ähnlich wie man das auch von Windows kennt.

Um nun per Kommandozeile Dateien und Ordner anzulegen oder zu betrachten, gibt es diverse Befehle:

## Wo bin ich? ##

Starten wir die Kommandozeile, befinden wir uns an einem ganz bestimmten Ordnerpfad. Diesen können wir sehen wenn wir den Befehl
```bash
pwd
```
eingeben. Es sollte dann so etwas wie

```bash
/home/<username>/
```
erscheinen (wobei statt <username\> der jeweilige Accountname zu sehen ist).
pwd steht übrigens für "print working directory", was soviel heißt wie: "gib den Namen des aktuellen Verzeichnisses aus".

## Inhalt eines Ordners betrachten ##

Um zu sehen, was in einem Ordner enthalten ist, benutzen wir den Befehl

```bash
ls
```

Damit werden alle Ordner und Dateien aufgelistet, die im aktuellen Verzeichnis enthalten sind.

## Ordner erstellen ##

Ein Ordner lässt sich mithilfe von

```bash
mkdir <Ordnername>
```

erstellen. <Ordnername\> sollte dabei mit einem geeigneteren Namen ersetzt werden.

## In ein anderes Verzeichnis wechseln ##

Um den Ordner zu wechseln, in dem wir uns gerade befinden, benutzen wir den Befehl __cd__ (change directory).

```bash
cd <Ordnername>
```

Befinden wir uns in einem Ordner und möchten in den darüberliegenden Ordner wechseln, machen wir das mittels

```
cd ..
```

### Kleines Beispiel ###


Wir befinden uns in unserem Home-Verzeichnis (um uns zu vergewissern, dass so ist, benutzen wir gleich noch einmal __pwd__), erstellen einen Ordner mit dem Namen Python-SoSe2016, und "bewegen uns" in diesen.
Dann benutzen wir noch einmal __pwd__, um festzustellen, wo wir nun sind.

```bash
pwd
mkdir Python-SoSe2016
cd Python-SoSe2016
pwd
cd ..
pwd
```

## Dateien lesen ##

Möchten wir den Inhalt einer einfachen Textdatei betrachten, hilft uns das Programm __cat__.

```bash
cat <Dateiname>
```

Mit dem obigen Befehl wird der Inhalt der Textdatei \<Dateiname\> in der Konsole ausgegeben.
Handelt es sich um einen längeren Text, der zu groß für das Terminal ist, können wir __less__ benutzen

```bash
less <Dateiname>
```

Wieder wird uns der Text angezeigt, aber diesmal können wir mithilfe der Pfeiltasten hoch- und runterscrollen.
Indem wir __q__ drücken, beenden wir das Programm wieder.




