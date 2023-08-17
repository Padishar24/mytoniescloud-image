# mytoniescloud image

[Image can be found here](https://hub.docker.com/r/padishar24/mytoniescloud)

# How to configure
Extract form my docker compose

    ports:
     - "8000:80"
    volumes:
     - /volume1/music/Hörspiele:/audiobooks:rw
     - /volume1/docker/appData/mytoniescloud:/appData:rw

- Map external port to internal port 80
- Map your media folder to "/audiobooks", probable "read" access is sufficient
- Map an abitrary folder tp "/appData", r/w is neccessary. This is optional. If not provided, data is stored in "/audiobooks/.mytoniescloud". Then r/w is mandatory.

# How media must be stored
Note: My media is stored in folders with following structure:
- /audiobooks
   - /artist1
      - /album1
        -  *.mp3
      - /album2
        -  *.mp3
   - /artist2
    -  ....

No other structure is tested! Please contact me, if you have any issues.
