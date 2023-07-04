# geojson-italia
Contiene i file GeoJSON con le georeferenziazioni di Regioni, Provincie e Comuni italiani

## Fonte dati
I dati di partenza sono stati presi dal sito ISTAT all'indirizzo 
https://www.istat.it/it/archivio/222527

## Ultimo aggiornamento ISTAT
`1° gennaio 2023`

## Post-processing
I dati di partenza sono poi stati "ridotti" tramite il servizio https://mapshaper.org

Successivamente, la conversione è stata effettuata sfruttando le librerie GDAL (https://gdal.org).

Nello specifico con il comando `ogr2ogr` compreso nel pacchetto:
```
$ ogr2ogr -f "GeoJSON" regioni.json Regioni_WGS84.json -t_srs EPSG:4326 -s_srs EPSG:32632

$ ogr2ogr -f "GeoJSON" provincie.json Provincie_WGS84.json -t_srs EPSG:4326 -s_srs EPSG:32632

$ ogr2ogr -f "GeoJSON" comuni.json Comuni_WGS84.json -t_srs EPSG:4326 -s_srs EPSG:32632
```
