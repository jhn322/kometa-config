# Kometa Config (Formerly Plex Meta Manager)

My Kometa config for automatically creating collections and overlays for Plex. These files were originally created using templates and has since then been rewritten/edited completely and updated regularly by me since 2021. As far as overlays go I have put an emphasis on providing useful info at a glance without going over the top, while having a very comprehensive yet not too overwhelming amount of collections.

For all lists and overlays to work you'll need to configure API tokens from Trakt, MyAnimeList, AniDB, TMDb and more in your config.yml file.

## Install (Docker Compose)

This is how to install Kometa using docker compose with a daily run schedule for collections, overlays and operations as a stack containing three containers.

1. Clone/download this repository.
2. Add **your** local Plex server IP-adress and [token](https://support.plex.tv/articles/204059436-finding-an-authentication-token-x-plex-token/) **and** change each library title to the exact(!) name your Plex libraries are named in the config.yml.
3. Many collections in this config require a unique API key/token/id for a service such as Trakt, MdbList and more. Below is a list of the ones in this repo and I would **highly recommend** you set them up for the best possible experience:

- [Trakt](https://metamanager.wiki/en/latest/config/trakt/)
- [TMDb](https://metamanager.wiki/en/latest/config/tmdb/)
- [MdbList](https://metamanager.wiki/en/latest/config/mdblist/)
- [OMDb](https://metamanager.wiki/en/latest/config/omdb/)
- [AniDB](https://metamanager.wiki/en/latest/config/anidb/)
- [MyAnimeList](https://metamanager.wiki/en/latest/config/myanimelist/)
- [Tautulli](https://metamanager.wiki/en/latest/config/tautulli/)

4. [Install docker with compose](https://www.theserverside.com/blog/Coffee-Talk-Java-News-Stories-and-Opinions/How-to-install-Docker-and-docker-compose-on-Ubuntu) or [Docker desktop](https://www.docker.com/products/docker-desktop/) for Windows/Mac (if you haven't already). Running locally with Python is also possible but not recommended in the long run, refer to the [wiki](https://metamanager.wiki/en/latest/kometa/install/local/).
5. Open terminal and navigate to your path:

```powershell
Linux: "cd /path/to/Kometa-folder"

Windows: "cd C:\path\to\Kometa-folder"

Mac: "cd ~/path/to/Kometa-folder"
```

6. Now paste this in the terminal to create the containers:

```powershell
Linux: "sudo docker-compose up -d"

Windows/Mac: "docker-compose up -d"
```

**Done!**

## Docker run (Optional/Testing)

If you for some reason don't want to use Docker compose, you can simply utilize the run commands to achieve the same result:

```powershell
Linux:
sudo docker run --restart=unless-stopped -d -v "/path/to/Kometa-folder/config:/config:rw" kometateam/kometa:develop -co --time 06:00
sudo docker run --restart=unless-stopped -d -v "/path/to/Kometa-folder/config:/config:rw" kometateam/kometa:develop -op --time 08:00
sudo docker run --restart=unless-stopped -d -v "/path/to/Kometa-folder/config:/config:rw" kometateam/kometa:develop -ov --time 09:00

Windows:
docker run --restart=unless-stopped -d -v "C:\path\to\Kometa-folder/config:/config:rw" kometateam/kometa:develop -co --time 06:00
docker run --restart=unless-stopped -d -v "C:\path\to\Kometa-folder/config:/config:rw" kometateam/kometa:develop -op --time 08:00
docker run --restart=unless-stopped -d -v "C:\path\to\Kometa-folder/config:/config:rw" kometateam/kometa:develop -ov --time 09:00

Mac:
docker run --restart=unless-stopped -d -v "~/path/to/Kometa-folder/config:/config:rw" kometateam/kometa:develop -co --time 06:00
docker run --restart=unless-stopped -d -v "~/path/to/Kometa-folder/config:/config:rw" kometateam/kometa:develop -op --time 08:00
docker run --restart=unless-stopped -d -v "~/path/to/Kometa-folder/config:/config:rw" kometateam/kometa:develop -ov --time 09:00
```

For testing purposes (single run):

```powershell
Linux: sudo docker run -it -v "/path/to/Kometa-folder/config:/config:rw" kometateam/kometa --run

Windows: docker run -it -v "C:\path\to\Kometa-folder/config:/config:rw" kometateam/kometa --run

Mac: docker run -it -v "~/path/to/Kometa-folder/config:/config:rw" kometateam/kometa --run
```

## Update Kometa

This will update Kometa to the latest branch version.

```powershell
Stable: docker pull kometateam/kometa
Develop: docker pull kometateam/kometa:develop
Nightly: docker pull kometateam/kometa:nightly
```

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

![image search api](https://i.imgur.com/5Ot6ziT.png)

**TV**

![image search api](https://i.imgur.com/4Z28s9A.png)

**Anime**

![image search api](https://i.imgur.com/kTwTjW8.png)

### Overlays examples

**Movies**

![image search api](https://i.imgur.com/cTeNiMb.png)

**TV**

![image search api](https://i.imgur.com/7cUfZ53.png)

**Remux**

![image search api](https://i.imgur.com/lcFOxiG.png)

### For more help go to the wiki: https://metamanager.wiki/en/latest/
