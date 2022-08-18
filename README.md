# MacOS-Fotos
Hier kommen paart Tips zur Apples Foto Mediathek

## Matadaten kopieren
Nach den Export von Videos geht das Erstellungsdatum und die GEO-Informationen verloren. Beim export mit iMovie auch.
Wenn das Orginal vorhanden ist, kann man die Daten kopieren.

## Wozu das ganze?
Damit exportierte oder sonst wie bearbeitete Bilder oder Videos wieder am richtigen Platz in der Foto Mediathek erscheinen.
Ein Zeitlupen-Video, welches in der Foto bearbeitet wurde ist immer noch sehr groß. Nach der bearbeitung z.B. in iMovie ist es viel kleiner. Enthält abe nicht mehr das orginale CreateDate und die GPS-Informationen.


***in wie weit es 100% die richtigen Parameter sind, kann ich nicht sagen. Für mich reicht es :-)***

Man brauch das Kommandozeilen Tool https://exiftool.org/, welches es für Windows und MacOS gibt.

```
exiftool -TagsFromFile srcimage.jpg "-all:all>all:all" targetimage.jpg
```

Nach paar Tests kann man den Parameter **-overwrite_original** benutzen. Damit wird verhindert, dass immer eine Kopie der bearbeiteten Datei erstellt wird. Bei Videos kann das schon 1GB oder mehr betragen.
Man kann die Metadaten zwischen verschiedenen Videoformaten anwenden.

```
exiftool -TagsFromFile srcimage.mov "-all:all>all:all" targetimage.mp4 -overwrite_original
```

Mann kann noch **CreateDate** auf **File Create** und **Modify Date** anwenden, damit es mehr wie Orginal aussieht

```
exiftool "-FileCreateDate<CreateDate" "-FileModifyDate<CreateDate" 2021-07-27_08-57-05.mp4
```
Man kann es auf 
```
exiftool "-FileCreateDate<CreateDate" "-FileModifyDate<CreateDate" C:\Video-Out
```

### Batch mit Drag and Drop Option
Einen Textdatei `exif-coppy_all.cmd` mit folgenden Inhalt erstellen 

```
set /p "orginal=Orginal-Datei: "
set /p "ziel=Ziel-Datei: "
c:\Tools\exiftool.exe -TagsFromFile %orginal% "-all:all>all:all" %ziel% -overwrite_original
c:\Tools\exiftool "-FileCreateDate<CreateDate" "-FileModifyDate<CreateDate" -api QuickTimeUTC %ziel%
```

### GPS Daten kopieren
Manchmal gib es ein paa Bilder die keine GPS Koordinaten haben.
- man filtert sie am besten via Inteligent Album raus.
- dannach exportiert man die Orginale (
- dann gps:all
- dannach können sie wieder importiert werden

```
exiftool -tagsfromfile C:\visual\filename.jpg -gps:all C:\thermal\filename.jpg
```

Auf einen Macbook
```
exiftool -TagsFromFile srcimage.jpg '-all:all>all:all' targetimage.jpg -overwrite_original
exiftool '-FileCreateDate<CreateDate' '-FileModifyDate<CreateDate' -ext .mp4 -r a:\A
```

## Live Fotos Beobachtungen
- die Auflösung, Dauer hängen von Gerät und der iOS Version
- die Bildrate ist von den Gegebenheiten abhängig und abends häufig nicht konstant
