### HACS
HACS is a community-driven AddOn store for HA. 
Installation for docker:
```
docker exec -it homeassistant bash
wget -O - https://get.hacs.xyz | bash -
exit
docker restart homeassistant
```
[Source](https://hacs.xyz/docs/setup/download/)

### Zigbee


### Spotify
Add through WebUI. If auth or redirect fails on initiation, delete /root/homeassistant/config2/.storage/application_credentials
This will reset the initiation.
[The guide](https://www.home-assistant.io/integrations/spotify/) says to use "https://my.home-assistant.io/redirect/oauth" as the redirect URI. This is correct. If you get a INVALID URI error, check the Url for the correct redirect URI

### Meross
[https://github.com/albertogeniola/meross-homeassistant](https://github.com/albertogeniola/meross-homeassistant)


### Sonarr
