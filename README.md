# docker-PLEX
Use docker-compose create

``` sh
git clone https://github.com/jason22432150/docker-PLEX.git
mv docker-PLEX/ PLEX/
cd PLEX
docker-compose up -d
```

This is docker-comporse.yml
```yml
version: "2.1"
services:
  plex:
    image: lscr.io/linuxserver/plex
    container_name: plex
    network_mode: host
    environment:
      - PUID=1000
      - PGID=1000
      - VERSION=docker
      - PLEX_CLAIM= #optional
    volumes:
      - /path/to/library:/config
      - /path/to/tvseries:/tv
      - /path/to/movies:/movies
      - /mnt:/mnt
    restart: unless-stopped
```

Then you can go 

http://[yourIP]:32400/web
