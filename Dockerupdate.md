# Updating Docker container

Updating the HA container, can be adapted and used for different containers.

## 0. Backup
Do yourself a favor

## 1. Get Info
The used image is ghcr.io/home-assistant/home-assistant:stable

run 'docker ps -a' and note the container ID (10065953d8f8), image (ghcr.io/home-assistant/home-assistant:stable) and name (homeassistant)

run 'docker images' and note the image ID of the image (d7dbbd3d21ec).

## 2. Get rid of old version
run
```
docker stop [CONTAINER ID]
docker rm [CONTAINER ID]
```
### Remove old images
when running 'docker images' you can see the IDs of the images you don't need anymore. 
You can remove them with 'docker image remove IMAGE-ID' (append -f to force)

## 3. Get new version and install
pull image and install just as in initial installtion (see Installation.md)

### Sources
https://www.whitesourcesoftware.com/free-developer-tools/blog/update-docker-images/
