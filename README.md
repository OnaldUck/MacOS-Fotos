# MacOS-Fotos
Hier kommen paart Tips zur Apples Foto Mediathek

## Matadaten kopieren
Nach den Export von Videos geht das Erstellungsdatum und die GEO-Informationen verloren. Beim export mit iMovie auch.
Wenn das Orginal vorhanden ist, kann man die Daten kopieren.


```
exiftool -TagsFromFile srcimage.jpg "-all:all>all:all" targetimage.jpg -overwrite_original
exiftool "-FileCreateDate<CreateDate" "-FileModifyDate<CreateDate" -ext .mp4 -r a:\A
```


Bei MacOS
```
exiftool -TagsFromFile srcimage.jpg '-all:all>all:all' targetimage.jpg -overwrite_original
exiftool '-FileCreateDate<CreateDate' '-FileModifyDate<CreateDate' -ext .mp4 -r a:\A
```

## Live Fotos Beobachtungen
- die Auflösung, Dauer hängen von Gerät und der iOS Version
- die Bildrate ist von den Gegebenheiten abhängig und abends häufig nicht konstant
