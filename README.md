av_chenyx06_ntv2
================

Vergleiche zwischen CHENyx06- und NTV2-Transformationen

Achtung
-------
In QGIS immer überprüfen, ob "on the fly transformation" ausgeschaltet ist, wenn man sie ausgeschaltet haben will. Da kann viel Schabernack passieren.


Vorbereitungen
--------------
1. Fixpunkte des ganzen Kantons von [catais.org](http://www.catais.org/geodaten/ch/so/kva/av/mopublic/shp/lv03/d/) herunterladen.
2. In QGIS unwichtige Attributspalten löschen damit die DBF-Datei kleiner wird.

Transformation mit NTv2
-----------------------
1. Die LV03-Shapedatei in QGIS in einem LV03-Projekt laden.
2. Der Layer als Shapedatei speichern. Als CRS CH1903+/LV95 wählen. 
3. Der Datumstransformationsdialog poppt auf: `CHENYX06a.gsb` wählen.
4. Mit `ogrinfo -al lfp.shp` kurz anprüfen, ob überhaupt was transformiert wurde.

Transformation mit CHENyx06
---------------------------
Wird direkt in der GeoKettle-Vergleichstransformation gemacht.


gdal_grid
---------

2592572.97,1213771.16 : xMax,yMax 2644719.18,1261330.18

2592500 1213500 2645000 1261500

52500 48000
5250 4800
2625 2400


gdal_grid -zfield fs -a invdist:power=2.0:radius1=500:radius2=500:max_points=5 -txe 2592500 2645000 -tye 1213500 1261500 -outsize 5250 4800 -of GTiff -ot Int16 -l vergleich_chenyx06_ntv2 vergleich_chenyx06_ntv2.shp vergleich_chenyx06_ntv2.tif

gdal_grid -zfield fs -a invdist:power=2.0:radius1=500:radius2=500:max_points=5 -txe 2592500 2645000 -tye 1213500 1261500 -outsize 2625 2400 -of GTiff -ot Int16 -l vergleich_chenyx06_ntv2 vergleich_chenyx06_ntv2.shp vergleich_chenyx06_ntv2.tif

```

```


```


```
