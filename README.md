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
