# Plex Meta Manager Config

My config of Plex Meta Manager for automatically creating collections and overlays to Plex. These files were originally created using templates and has since then been rewritten completely and updated regularly by me since 2021. For all lists and overlays to work you'll need to configure API tokens from Trakt, MyAnimeList, AniDB, TMDb among others in your config.yml file.

## Install (Docker Compose)

This will install Plex meta manager using docker compose with a daily run schedule for collections, overlays and operations as three seperate containers.

1. Download this repository.
2. Rename folder to "Plex-meta-manager".
3. Install docker with compose or docker desktop if you haven't already.
4. Open terminal and navigate to your path:

**Windows:** "cd C:\path\to\Plex-meta-manager"

**Linux:** "cd /path/to/Plex-meta-manager"

5. Now paste this in the terminal to create the containers:

**Windows:** "docker-compose up -d"

**Linux:** "sudo docker-compose up -d"

**Done!**

## Docker run

This will run through the entire config one time, It will **not** keep updating on a schedule.

**Windows:** "docker run -it -v "C:\path\to\plex-meta-manager/config:/config:rw" meisnate12/plex-meta-manager --run"

**Linux:** "sudo docker run -it -v "/path/to/Plex-meta-manager/config:/config:rw" meisnate12/plex-meta-manager --run"

## Targeted library types:

- Anime
- Audiobooks
- Movies
- Music
- Remux
- Soundtracks
- TV
- Videos

### Collections examples

**Movies**

![image search api](https://i.imgur.com/Q6njLZ9.png)

**Anime**

![image search api](https://i.imgur.com/dbuw1Gv.png)

### Overlays examples

**Movies**

![image search api](https://i.imgur.com/cTeNiMb.png)

**Remux**

![image search api](https://i.imgur.com/lcFOxiG.png)

### For more help go to the wiki: https://metamanager.wiki/en/latest/
