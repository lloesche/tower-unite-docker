# tower-unite-docker
Tower Unite Server in a Docker Container

# Docker example
```
$ docker run -d --rm \
    -p 27015-27050:27015-27050/tcp \
    -p 27015-27050:27015-27050/udp \
    -p 7777-7780:7777-7780/udp \
    -p 3478:3478/udp \
    -p 4379-4380:4379-4380/udp \
    -e MaxPlayers=64
    lloesche/tower-unite
```

# Docker+systemd example
```
# curl -o /etc/systemd/system/tower-unite.service https://raw.githubusercontent.com/lloesche/tower-unite-docker/master/tower-unite.service
# systemctl daemon-reload
# systemctl enable tower-unite
# systemctl start tower-unite
```

Optionally create a file `/etc/sysconfig/tower-unite` with contents like:
```
ServerTitle=Great Tower Unite Server
MaxPlayers=64
SteamLoginToken=somevalidtoken
```
