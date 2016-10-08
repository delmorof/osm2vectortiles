```bash
make fast 

docker-compose up -d postgis

docker-compose run import-external

cd import 

Planet
- wget http://planet.osm.org/pbf/planet-latest.osm.pbf

Europe
- wget http://download.geofabrik.de/europe-latest.osm.pbf

italy-centro
- wget http://download.geofabrik.de/europe/italy/centro-latest.osm.pbf

docker-compose run import-osm

docker-compose run import-sql

docker-compose run \
  -e BBOX="10.88,43.58,11.57,43.97" \
  -e MIN_ZOOM="10" \
  -e MAX_ZOOM="16" \
  export
  
Ensure you have export/planet.mbtiles file present to merge the jobs into. 
Reuse a low level zoom extract generated earlier or download an existing low level zoom extract from http://osm2vectortiles.org/downloads/. Ensure you have insalled sqlite3 drivers.

wget https://raw.githubusercontent.com/mapbox/mbutil/master/patch
chmod +x patch

sudo chown geoin export/tiles.mbtiles
./patch "./export/planet_z0-z8.mbtiles" "./export/tiles.mbtiles"
```
