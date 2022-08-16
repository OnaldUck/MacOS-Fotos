# MacOS-Fotos

```
exiftool -TagsFromFile srcimage.jpg "-all:all>all:all" targetimage.jpg -overwrite_original
exiftool "-FileCreateDate<CreateDate" "-FileModifyDate<CreateDate" -ext .mp4 -r a:\A
```
Bei MacOS
```
exiftool -TagsFromFile srcimage.jpg '-all:all>all:all' targetimage.jpg -overwrite_original
exiftool '-FileCreateDate<CreateDate' '-FileModifyDate<CreateDate' -ext .mp4 -r a:\A
```
