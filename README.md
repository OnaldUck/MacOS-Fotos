# MacOS-Fotos
Hier kommen paart Tips zur Apples Foto Mediathek

## Matadaten kopieren
Nach den Export von Videos geht das Erstellungsdatum und die GEO-Informationen verloren. Beim export mit iMovie auch.
Wenn das Orginal vorhanden ist, kann man die Daten kopieren.

***in wie weit es 100% die richtigen Parameter sind, kann ich nicht sagen. Für mich reicht es :-)***

Man brauch das Kommandozeilen Tool https://exiftool.org/, welches es für Windows und MacOS gibt.

```
exiftool -TagsFromFile srcimage.jpg "-all:all>all:all" targetimage.jpg
```

Nach paar Tests kann man den Parameter **-overwrite_original** benutzen. Damit wird verhindert, dass immer eine Kopie der bearbeiteten Datei erstellt wird. Bei Videos kann das schon 1GB oder mehr betragen.
Man kann die Metadaten zwischen

```
exiftool -TagsFromFile srcimage.mov "-all:all>all:all" targetimage.mp4 -overwrite_original
```




```
exiftool "-FileCreateDate<CreateDate" "-FileModifyDate<CreateDate" -ext .mp4 C:\A
```

```
exiftool "-FileCreateDate<CreateDate" "-FileModifyDate<CreateDate" 2021-07-27_08-57-05.mp4
```
###
```
set /p "quelle=quelle Datei: "
set /p "ziel=ziel Datei: "
c:\Tools\exiftool.exe -TagsFromFile %quelle% "-all:all>all:all" %ziel% -overwrite_original
```

### GPS Daten kopieren

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
