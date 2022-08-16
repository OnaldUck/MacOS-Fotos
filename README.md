# MacOS-Fotos
Hier kommen paart Tips zur Apples Foto Mediathek

## Matadaten kopieren
Nach den Export von Videos geht das Erstellungsdatum und die GEO-Informationen verloren. Beim export mit iMovie auch.
Wenn das Orginal vorhanden ist, kann man die Daten kopieren.

Man brauch das Kommandozeilen Tool https://exiftool.org/

```
exiftool -TagsFromFile srcimage.jpg "-all:all>all:all" targetimage.jpg -overwrite_original
```
Nach paar Tests kann man den Parameter **-overwrite_original** benutzen. Damit wird verhindert, dass immer eine Kopie der bearbeiteten Datei erstellt wird. Bei Videos kann das schon 1GB oder mehr betragen.

```
exiftool "-FileCreateDate<CreateDate" "-FileModifyDate<CreateDate" -ext .mp4 -r a:\A
```



Auf einen Macbook
```
exiftool -TagsFromFile srcimage.jpg '-all:all>all:all' targetimage.jpg -overwrite_original
exiftool '-FileCreateDate<CreateDate' '-FileModifyDate<CreateDate' -ext .mp4 -r a:\A
```

## Live Fotos Beobachtungen
- die Auflösung, Dauer hängen von Gerät und der iOS Version
- die Bildrate ist von den Gegebenheiten abhängig und abends häufig nicht konstant
