# Updating Docker container

Updating the plex container, can be adapted and used for different containers.

## useful commands
```
docker ps -a      list containers
docker images     list images
docker stop, start, restart, pause, kill CONTAINER
```

## 0. Backup
Do yourself a favor

## 1. Get Info
The used image is lscr.io/linuxserver/plex

run 'docker ps -a' (you can omit the -a if plex is running) and note the container ID (924818f74a8a), image (lscr.io/linuxserver/plex) and name (plex)

run 'docker images' and note the image ID of the image (c34dee5bf1ba).

## 2. Get rid of old version
run
```
docker stop [CONTAINER ID]
docker rm [CONTAINER ID]
```
### Remove old images
when running 'docker images' you can see the IDs of the images you don't need anymore. 
You can remove them with 'docker image remove IMAGE-ID'

## 3. Get new version
```
docker pull lscr.io/linuxserver/plex:latest
```

## 4. Create new container with new image
```
docker run -d \
  --name=plex \
  --net=host \
  -e PUID=1000 \
  -e PGID=1000 \
  -e VERSION=latest \
  -e PLEX_CLAIM=claim-token \
  -v /mnt/Seagate/dockerplex/config:/config \
  -v /mnt/Seagate/Videos/Movies:/mnt/Seagate/Videos/Movies \
  -v /mnt/Seagate/Videos/Shows:/mnt/Seagate/Videos/Shows \
  -v /mnt/Seagate/dockerplex/transcode:/transcode \
  --restart unless-stopped \
  lscr.io/linuxserver/plex
docker start plex
```

### Sources
https://www.whitesourcesoftware.com/free-developer-tools/blog/update-docker-images/
