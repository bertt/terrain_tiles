
Source:

```
$ wget https://download.pdok.nl/rws/ahn3/v1_0/5m_dtm/M5_39EN1.ZIP
```

Extract: M5_39EN1.TIF

Fill nodata values in QGIS using gdal:fillnodata

```
$ gdalwarp -t_srs EPSG:4326 M5_39EN1.TIF -dstnodata 0 M5_39EN1.TIF_4326.TIF -overwrite
```

```
$ rio rgbify -b -10000 -i 0.1 --min-z 0 --max-z 16 -j 24 --format png M5_39EN1.TIF_4326.TIF output.mbtiles
```

```
$ mb-util output.mbtiles tiles
```
