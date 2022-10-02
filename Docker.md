These need editted for your own use. At the very least anything between `<` and `>` needs set for your environment.
For windows, and other devices all of the paths below will need set correctly for the mounts.

#### Docker Compose

```bash
---
version: "3.3"
services:
  sickchill:
    container_name: sickchill
    image: sickchill/sickchill
    environment:
      - PUID=1000
      - PGID=1000
      - TZ=America/New_York
      - USERDIR=/home/<username>/sickchill
      - SHOWS_AND_DOWNLOADS_ROOT=<path/to/shows/and/downloads/drive>
    volumes:
      - $USERDIR/sickchill:/config
      - $USERDIR/sickchill:/data
      - $SHOWS_AND_DOWNLOADS_ROOT:$SHOWS_AND_DOWNLOADS_ROOT
    ports:
      - 8081:8081
    network_mode: host
    restart: unless-stopped
```

#### Docker run

```bash
docker run -dit --user 1000:1000 --name sickchill --restart=always \
-e TZ=America/New_York -e PUID=1000 -e PGID=1000
-v /home/<username>/sickchill:/config \
-v /home/<username>/sickchill:/data \
-v <path/to/shows/and/downloads/drive>:<path/to/shows/and/downloads/drive> \
-v /etc/localtime:/etc/localtime:ro \
-p 8081:8081 sickchill/sickchill
```
