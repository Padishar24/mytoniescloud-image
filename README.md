# Description
Introducing MyToniesCloud, the ultimate web app designed to revolutionize the way you manage and enjoy your children's audiobooks! With its seamless integration with NAS or RaspberryPI devices in your local network, this innovative app allows you to effortlessly upload and organize your favorite audio content onto creative tonies.

Gone are the days of limited options for changing the content on your tonies. MyToniesCloud provides a user-friendly platform that empowers parents and caregivers to easily customize their children's listening experience. Whether it's swapping out beloved bedtime stories or introducing new educational podcasts, this app puts you in control of what your little ones hear.

One of the standout features of MyToniesCloud is its ability to upload not only locally stored media files but also free online podcasts that offer parseable feeds. This means that you can expand your library beyond just physical audiobooks, giving you access to an endless array of captivating storytelling from around the world.

Designed with young children in mind, MyToniesCloud offers a safe and intuitive interface suitable for kids aged 3 years and older. The simple navigation ensures that even little ones can independently select their preferred tonie and immerse themselves in hours of delightful audio entertainment.

It's important to note that MyToniesCloud is an independent creation and has no affiliation with Boxine GmbH, the producer of tonieboxes. 

Say goodbye to monotonous playback routines and hello to endless possibilities with MyToniesCloud! Experience a whole new level of convenience as you effortlessly curate personalized audio experiences for your child. Don't miss out on this game-changing app – try MyToniesCloud today!

# Docker Image

[Image can be found here](https://hub.docker.com/r/padishar24/mytoniescloud)

# How to configure
### Extract from my docker compose

    ports:
     - "8000:80"
    volumes:
     - /volume1/music/Hörspiele:/audiobooks:rw
     - /volume1/docker/appData/mytoniescloud:/appData:rw

- Map external port to internal port 80
- Map your media folder to "/audiobooks", probable "read" access is sufficient
- Map an arbitrary folder to "/appData", r/w is neccessary. This is optional. If not provided, data is stored in "/audiobooks/.mytoniescloud". Then r/w is mandatory.

### Synology UI
On my Synology DS220+ the container configurations looks like:

![image](https://github.com/Padishar24/mytoniescloud-image/assets/56674769/fc5921b4-1d03-4ecb-b93d-ed3f2271de19)

I also gave user "SYSTEM" read/write access to folder 'AppData'

![image](https://github.com/Padishar24/mytoniescloud-image/assets/56674769/9dfd596d-7c1a-420a-8820-1acd679d7e71)


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

No other structure was tested! Please contact me, if you have any issues.

# Podcasts
Here are some examples for free german podcasts best suited for our little ones:
- https://www.ohrenbaer.de/podcast/podcast.feed.podcast.xml
- https://kinder.wdr.de/radio/diemaus/audio/gute-nacht-mit-der-maus/diemaus-gute-nacht-104.podcast
- https://kinder.wdr.de/radio/diemaus/audio/diemaus-60/diemaus-60-106.podcast
- https://feeds.br.de/anna-und-die-wilden-tiere/feed.xml
