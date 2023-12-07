# Plex Meta Manager Config

My config of Plex Meta Manager for automatically creating collections and overlays to Plex. These files were originally created using templates and has since then been rewritten completely and updated regularly by me since 2021. For all lists and overlays to work you'll need to configure API tokens from Trakt, MyAnimeList, AniDB, TMDb among others in your config.yml file. All collections, Overlays and Operations are configured to update on a daily schedule.

## Install

1. Download this repository.
2. Rename folder to "Plex-meta-manager".
3. Recommended to install docker with compose or docker desktop if you haven't already, otherwise local install with python 3.8 will do.
4. Open terminal and navigate to your path:

**Windows:** "cd C:\path\to\Plex-meta-manager"

**Linux:** "cd /path/to/Plex-meta-manager"

5. Now paste this in the terminal to create the containers:

**Windows:** "docker-compose up -d"

**Linux:** "sudo docker-compose up -d"

**Done!**

### One time run:

**Windows:** "docker run -it -v "C:\path\to\plex-meta-manager/config:/config:rw" meisnate12/plex-meta-manager --run"

**Linux:** "sudo docker run -it -v "/path/to/Plex-meta-manager/config:/config:rw" meisnate12/plex-meta-manager --run"

### Update container

docker pull meisnate12/plex-meta-manager

### This will create collections and overlays to these types of libraries:

1. Anime
2. Audiobooks
3. Movies
4. Music
5. Remux
6. Soundtracks
7. TV
8. Videos

### Collections example

![image search api](https://i.imgur.com/hURTISN.png)

### Overlays example

![image search api](https://i.imgur.com/aOjcjQh.png)

### For more help go to the wiki: https://metamanager.wiki/en/latest/
