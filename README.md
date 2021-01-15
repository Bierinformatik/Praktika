# Praktika

## Jede Gruppe muss dieses Repository forken
## Dann muss jede Gruppe in ihrem Fork ein Verzeichnis erstellen, das Als Namen den Gruppennamen trägt (zB. Gruppe1 oder Gruppe45)
## Alles, was für die Betreuer sichtbar sein soll, muss in dem erstellten Verzeichnis (oder in Unterverzeichnissen) stehen, um Konflikte zu vermeiden 

# Git 

Damit wir eine bessere übersicht haben was ihr getan habt und wo ihr grade seid, soll euer code und eure fortschritte im git liegen.

Dazu [meldet euch bitte auf github an](https://github.com/join "github sign up"), forked dieses Repository einmal pro Praktikumsgruppe und fügt die anderen Gruppenmitgleider als "maintaner"- members hinzu. 

![fork button location](.github/fork_button.jpg) 
 
Members kann man im Seitenpanel aud der linken Seite unter dem vorletztem Punkt  "Members"  zu einem Repository hinzufügen. Nachdem die anderen Mitglieder hinzugefügt sind sollte unter in ihrem account das repository erscheinen. 

dann könnt ihr eure repositories mit *git clone* auf eure lokalen maschinen ziehen. In etwa so:

```
git clone git@github.com:Praktika(< change this !!! )/praktikum.git
```
euren jeweiligen link bekommt ihr unter dem grünen "Code" button..


Für den Komfort empfiehlt es sich gitlab mit einem ssh-schlüssel zu benutzen. Natürlich geht es auch ohne, aber mit ist praktisch.
Fügt dazu den Inhalt eures öffentlichen Schlüssels in eurem github Profil (rechts ganz oben, "Settings") unter dem punkt  *SSH and GPG keys* in das entsprechende textfeld.
Wie man einen ssh-schlüssel erstellt steht weiter unten.

Um eure lokalen änderungen in das gruppen repository upzudaten, schaut euch eine von den vielen git basics anleitungen im Netz an.

Ein üblicher simmpler workflow mit status check ist:
```
# updaten des lokalen repositories auf den neuesten stand:
git pull
# was verändern
# übersicht verschaffen was man so verändert hat:
git status
# veränderte dateien hinzufügen
git add dateiname
# jetzt hat  sich der status geändert ...
git status
# im commit beschreiben was man verändert hat, möglichst mit descriptiven texten:
git commit -m " really dunno what i changed , but i will commit anyway , allthough I couuld have broken something i`m not aware of"
# lokalen commit in remote repository pushen 
git push
```


# Computer an der bioinf 

Viele Aufgaben könnt ihr gut auf euren eigenen Rechnern erledigen, insbesondere mit einem relativ leistungsstarken. Falls benötigt hat jede praktikumsgruppe zu einemm rechner an der bioinformatik zugag über ssh. dort liegen auch für den spteren verlauf die entsprechenden genome, die müsst ihr also nicht auf eure rechner laden.

Um auf die rechner zuzugreifen empfiehlt sich ein ssh-schlüssel und ein eintrag in die '.ssh/config'.

### ssh schlüssel erstellen

wenn ihr noch keinen ssh schlüssel habt lässt sich mit 
```
cd ~/.ssh
ssh-keygen
```
einer erstellen.

Angenommen ihr habt den schlüssel *praktikum* genannt sollten jetzt  in .ssh die dateien "praktikum" und "praktikum.pub" liegen.

### ssh config
```
# ~/.ssh/config
Host prak
        kxx.bioinf.uni-leipzig.de
        user   praktikum0x  (hier den username den ihr von uns bekommt)
        Identityfile  ~/.ssh/praktikum
```

damit der ihr euch per ssh-schlüssel auf den rechner anmelden könnt müsst ihr einmalig den ssh schlüssel auf die jeweilige maschine kopieren.

```
ssh-copy-id -i .ssh/praktikum user@prak.bioinf.uni-leipzig.de 
```
wobei ihr *prak.bioinf.uni-leipzig.de* mit der adresse eurer zugewiesenen maschine und *user* mit eurem usernamen ersetzen müsst.

danach sollte man mit 

```
ssh prak
``` 
eine verbindung aufbauen können


