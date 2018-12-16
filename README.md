# docker-cacheboxserver
A Container for CBS Cacheboxserver

More information about cachebox and Cacheboxserver find here: https://geoclub.de/forum/viewforum.php?f=114


Installation steps:

Server running with ubuntu and docker 

mkdir /docker/data/cbs
  # copy your local cachebox database to this folder
cp cachebox.db3 /docker/data/cbs

docker run -d --restart=always \
  -p 8085:8085 \
  -e PUID=1000 -e PGID=1000 \
  --name=cacheboxserver \
  -v /docker/data/cbs:/cbs/cachebox \
  homersim1/cacheboxserver:latest


  # nach dem ersten "docker run", um alle Dateien erstell zu können
docker restart cachebox


# access your server via 
<IP-Adress>:80885/cbserver
