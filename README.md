# Praktika

## Jede Gruppe muss dieses Repository forken
## Dann muss jede Gruppe in ihrem Fork ein Verzeichnis erstellen, das Als Namen den Gruppennamen trägt (zB. Gruppe1 oder Gruppe45)
## Alles, was für die Betreuer sichtbar sein soll, muss in dem erstellten Verzeichnis (oder in Unterverzeichnissen) stehen, um Konflikte zu vermeiden 

# Git 

Damit wir eine bessere Übersicht haben was ihr getan habt und wo ihr grade seid, sollen euer Code und eure Fortschritte im Git liegen.

Dazu [meldet euch bitte auf github an](https://github.com/join "github sign up"), forked dieses Repository EINMAL pro Praktikumsgruppe und fügt die anderen Gruppenmitgleider als "maintaner"- members hinzu. 

![fork button location](.github/fork_button.jpg) 
 
Members kann man im Seitenpanel aud der linken Seite unter dem vorletztem Punkt  "Members"  zu einem Repository hinzufügen. Nachdem die anderen Mitglieder hinzugefügt sind sollte unter in ihrem Account das Repository erscheinen. 

Dann könnt ihr eure Repositories mit *git clone* auf eure lokalen Maschinen ziehen. In etwa so:

```
git clone git@github.com:Praktika(< change this !!! )/praktikum.git
```

Euren jeweiligen Link bekommt ihr unter dem grünen "Code" button..


Für den Komfort empfiehlt es sich GitHub mit einem SSH-Schlüssel zu benutzen. Natürlich geht es auch ohne, aber mit ist praktisch.
Fügt dazu den Inhalt eures öffentlichen Schlüssels in eurem Github Profil (rechts ganz oben, "Settings") unter dem Punkt  *SSH and GPG keys* in das entsprechende Textfeld.
Wie man einen SSH-Schlüssel erstellt steht weiter unten.

Um eure lokalen Änderungen in das Gruppen Repository zu übernehmen, schaut euch eine von den vielen Git basics Anleitungen im Netz an.

Ein üblicher simpler Workflow mit Status check ist:
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

Viele Aufgaben könnt ihr gut auf euren eigenen Rechnern erledigen, insbesondere mit einem relativ Leistungsstarken. 
Falls benötigt hat jede Praktikumsgruppe zu einem Rechner an der Bioinformatik (Zugang über SSH). 
Dort liegen auch für den späteren Verlauf die entsprechenden Genome, die müsst ihr also nicht auf eure Rechner laden.

Um auf die Rechner zuzugreifen empfiehlt sich ein SSH-Schlüssel und ein eintrag in die '.ssh/config'.

### SSH Schlüssel erstellen

Wenn ihr noch keinen SSH Schlüssel habt lässt sich mit 

```
cd ~/.ssh
ssh-keygen
```
einer erstellen.

Angenommen ihr habt den Schlüssel *praktikum* genannt sollten jetzt  in .ssh die dateien "praktikum" und "praktikum.pub" liegen.

### ssh config
```
# ~/.ssh/config
Host prak
        kxx.bioinf.uni-leipzig.de
        user   praktikum0x  (hier den username den ihr von uns bekommt)
        Identityfile  ~/.ssh/praktikum
```

Damit ihr euch per SSH-Schlüssel auf den Rechner anmelden könnt müsst ihr ihn einmalig auf die jeweilige Maschine kopieren.

```
ssh-copy-id -i .ssh/praktikum user@prak.bioinf.uni-leipzig.de 
```

wobei ihr *prak.bioinf.uni-leipzig.de* mit der Adresse eurer zugewiesenen Maschine und *user* mit eurem Usernamen ersetzen müsst.

Danach sollte man mit 

```
ssh prak
``` 
eine Verbindung aufbauen können


