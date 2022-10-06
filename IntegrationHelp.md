### HACS
HACS is a community-driven AddOn store for HA. It streamlines installing addons from github.
1. Installation for docker:
```
docker exec -it homeassistant bash
wget -O - https://get.hacs.xyz | bash -
exit
docker restart homeassistant
```
2. Configure:
In HA > Settings > Devices > Add Integration > search for HACS
follow instructions (accepting stuff, linking github)
HACS should now show up in HA's sidebar.

[Source](https://hacs.xyz/)

### Zigbee


### Spotify
Add through WebUI. If auth or redirect fails on initiation, delete /root/homeassistant/config2/.storage/application_credentials
This will reset the initiation.
[The guide](https://www.home-assistant.io/integrations/spotify/) says to use "https://my.home-assistant.io/redirect/oauth" as the redirect URI. This is correct. If you get a INVALID URI error, check the Url for the correct redirect URI

### Meross LAN
Can be installed with HACS.
https://github.com/krahabb/meross_lan

Adding device: in your Meross App you can see the MAC address. With this you can find the device's IP in your router's network view.
irst, use cloud retrieval with empty key, log in and get the key. Then change to user set. Or leave on cloud.
"auto" protocoll works, "http" will be chosen, most likely.

HA needs to be restarted between adding multiple devices.

### Sonarr
