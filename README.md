# Projektarbeit-Synthesizer

Dieses Repo ist in erster Linie für den Austausch von Dateien (LTspice-Modelle, Simulationen, Bauteilbibs etc.) gedacht.
Die Ordnerstruktur ist wie folgt: \
[ltspice/lib](./ltspice/lib/): hier könnt ihr eure Bauteilmodelle eintragen. \
[ltspice/<Modul>](./ltspice/): hier kann jeder einen Ordner mit dem Namen seines Moduls (VCO,VCF,VCA,ASMR,Sequencer,Netzteil etc.) erstellen und Simu-Dateien ablegen. 

Ansonsten erstellt jeder einen Ordner mit dem Namen seines Moduls und packt dort
Sachen rein, von denen er denkt, dass andere das sehen sollten.


## Nutzung des Repositorys

### Git-Konfiguration

Falls ihr noch nicht so viel Erfahrung mit Git habt hier ein kleines Intro.
Der Git-Config müsst ihr euren Namen und eure E-Mail-Adresse hinzufügen.

```bash
git config --global user.name "<Vorname> <Nachname>"
git config --global user.email "<verwendete E-Mail>"
```

Ihr solltet noch mit `git remote add origin git@github.com:tsedlmeier/Synthesizer.git` das Repo
unter dem Namen "origin" speichern (wird im weiteren Verlauf einfacher).

### SSH-Key eurem Git-Account hinzufügen

Damit könnt ihr Commits und Pulls durchführen, ohne dabei jedesmal euren Benutzernamen und Passwort
eingeben zu müssen. Dafür gebt ihr im Terminal `ssh-keygen` ein und wählt Pfad zum Key und Paraphrase (kann leer sein also einfach 2x Enter).
Jetzt sollte in eurem Home-Verzeichnis in dem Ordner ".ssh" eine Datei "id_<NAME>.pub" liegen. Den Inhalt
dieser Datei kopiert ihr bei eurem Git-Account im Browser unter "Settings -> SSH and GPG-Keys -> New
SSH-Key". Gebt eurem Key noch einen Namen.

### Klonen des Repos

Um das Repository auf eurem lokalen Rechner zu ziehen, müsst ihr dieses erstmal klonen (vorher Git konfigurieren!!!).

Das geschieht mit `git clone git@github.com:tsedlmeier/Synthesizer.git`.

### Änderungen an den Dateien durchführen

Ihr könnt mit `git checkout -b <BRANCH>` einen neuen Branch erstellen. (Ist für LTspice-Modelle etc.) eventuell etwas Overkill.

Änderungen ins Repo ziehen:

1. `git add <files>` 
2. `git commit -m "<kurze Nachricht an die Anderen was geändert wurde>"`
3. `git push`

### Lokales Repo aktualisieren

Wenn ihr die aktuellen Änderungen runterziehen wollt, dann geht das mit

```bash
git fetch origin
git pull --ff-only origin main
```

Eventuell vorhandene Branches müssen demnach auch aktualisiert werden. Dafür geht ihr in den Branch
und führt den Befehl `git rebase main` aus.

## Häufige Git-Befehle

|Kommando|Beschreibung|
|--------|------------|
|`git add <Files or Directory>`|Aktualisiert den Index mit den neuen Files|
|`git rm <Files or Directory>`|Entfernt die Files oder Directories vom Index|
|`git commit -m "<Message>"`|Erstellt einen Commit mit der Message, die mit -m angeben wird|
|`git push origin <Branch>`|Pusht die Daten vom Branch zu origin (Remote-Repo). Es sollte ein Pull-Request erzeugt werden|
|`git fetch origin`|Holt sich die Änderungen aus dem Remote-Repo "origin" (aber keine Aktualisierung des lokalen Repos!)|
|`git pull --ff-only origin main`|Aktualisiert den main-Branch des lokalen Repos (**im main-Branch ausführen!**) im Fast-Forward-Mode|
|`git checkout <Branch>`|Wechselt in den angegebenen Branch|
|`git checkout -b <Branch>`|Erstellt den angegebenen Branch und wechselt in diesen|
|`git status`|Zeigt anstehende Änderungen im aktuellen Branch an|
|`git log`|Zeigt die Commit Logs an|

