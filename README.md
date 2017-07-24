# rpi-home-assistant
Raspberry pi Dockerfile for Home Assistant Based off of lroguet/rpi-home-assistant.
Includes:
 - Modified lib-coap lib for Ikea Tradfri lights (https://home-assistant.io/components/tradfri/)
 - Docker for access to parent docker containers (running scripts, container info, etc)

```
# docker-compose.yml
hass:
  container_name: home-assistant
  image: mrono/rpi-home-assistant
  restart: 'always'
  net: host
  volumes:
    - /home/pi/home-assistant/configuration:/config
    - /etc/localtime:/etc/localtime:ro
    - /var/run/docker.sock:/var/run/docker.sock
```
