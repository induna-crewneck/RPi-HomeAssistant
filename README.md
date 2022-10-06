# RPi-HomeAssistant

## Installation
Using Docker container on pre-existing RaspberryPi setup (DietPi)

### 1. install
Pull image (might be optional)
```
docker pull homeassistant/home-assistant
```

Adjust Timezone [(TZ list)](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones#List), config location and run this block to install:
```
docker run -d \
  --name homeassistant \
  --privileged \
  --restart=unless-stopped \
  -e TZ=Europe/Berlin \
  -v /root/homeassistant/config:/config \
  --network=host \
  ghcr.io/home-assistant/home-assistant:stable
```

afterwards run
```
docker start homeassistant
```

### 2. WebUI
HomeAssistant can now be reached under port 8123

## Useful commands
```
docker ps -a      list containers
docker images     list images
docker restart homeassistant
docker stop, start, restart, pause, kill CONTAINER
```
