docker-compose up -d postgis

docker-compose run import-external

#Planet
# wget http://planet.osm.org/pbf/planet-latest.osm.pbf

#Europe
# wget http://download.geofabrik.de/europe-latest.osm.pbf

#italy-centro
wget http://download.geofabrik.de/europe/italy/centro-latest.osm.pbf

docker-compose run import-osm
