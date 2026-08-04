# 🚀 Kometa Config (Formerly Plex Meta Manager)

My Kometa config for automatically creating collections and overlays for Plex. These files were originally created using templates and has since then been rewritten/edited completely and updated regularly by me since 2021. As far as overlays go I have put an emphasis on providing useful info at a glance without going over the top, while having a very comprehensive yet not too overwhelming amount of collections.

### ❤️ Sponsor

If this config has been useful to you and you'd like to show your appreciation, considered [becoming a GitHub Sponsor](https://github.com/sponsors/jhn322). thanks :)

## ⚙️ Installation Guide (Docker Compose)

> [!NOTE]
> How to install Kometa using docker compose with a daily run schedule for collections, overlays and operations as a stack of three containers.

### Prerequisites

Before installation, you'll need API keys from these services for full functionality:

- [TMDb](https://metamanager.wiki/en/latest/config/tmdb/)
- [MdbList](https://metamanager.wiki/en/latest/config/mdblist/)
- [OMDb](https://metamanager.wiki/en/latest/config/omdb/)
- [MyAnimeList](https://metamanager.wiki/en/latest/config/myanimelist/)
- [Tautulli](https://metamanager.wiki/en/latest/config/tautulli/)
- ~~[Trakt](https://metamanager.wiki/en/latest/config/trakt/)~~ (deprecated)
- ~~[AniDB](https://metamanager.wiki/en/latest/config/anidb/)~~ (deprecated)

### Option 1: Docker Compose (Recommended)

1. Clone/download this repository.
2. Add **your** local Plex server IP address and [token](https://support.plex.tv/articles/204059436-finding-an-authentication-token-x-plex-token/). Then open `config.yml` and rename **each library name under `libraries:`** to **exactly** match the corresponding library name in your Plex server (including capitalization and spaces).
3. [Install docker with compose](https://www.theserverside.com/blog/Coffee-Talk-Java-News-Stories-and-Opinions/How-to-install-Docker-and-docker-compose-on-Ubuntu) or [Docker desktop](https://www.docker.com/products/docker-desktop/) for Windows/Mac (if you haven't already). Running locally with Python is also possible but not recommended in the long run, refer to the [wiki](https://metamanager.wiki/en/latest/kometa/install/local/).
4. Open terminal and navigate to your path:

```powershell
Linux: "cd /path/to/Kometa-folder"

Windows: "cd C:\path\to\Kometa-folder"

Mac: "cd ~/path/to/Kometa-folder"
```

5. Now paste this in the terminal to create the containers:

```powershell
Linux: "sudo docker-compose up -d"

Windows/Mac: "docker-compose up -d"
```

**Done!**

> [!TIP]
> External lists (like Trakt or Letterboxd) can sometimes lead to errors if the list owner deletes the list or changes its URL. To find and identify these dead links in your config files, consider using my [YAML URL Checker](https://github.com/jhn322/dead-link-checker) script. It scans your configuration on a schedule and report any inaccessible list URLs from the provided .yml files to Discord, helping to maintain an error-free Kometa config.

### Option 2: Combined Container

> [!NOTE]
> An alternative approach is to use a single container that runs all 3 different library operations continuously. To use this:
>
> 1. Rename the original `docker-compose.yml` to `docker-compose-original.yml`
> 2. Rename `docker-compose COMBINED.yml` to `docker-compose.yml`
> 3. Run the combined container using the same method as in previous step.

> [!WARNING]
> While simpler and faster to finish its run, the combined approach is generally not recommended for Plex servers with larger libraries. I've found running all operations continuously, in order according to the config.yml can potentially cause Plex to become unresponsive and/or crash. The separated container approach is more stable and recommended, but takes longer to complete.

### Option 3: Docker Run Commands

If for some reason you don't want to use Docker compose, simply utilize the run commands to achieve the same result:

```powershell
Linux:
sudo docker run --restart=unless-stopped -d -v "/path/to/Kometa-folder/config:/config:rw" kometateam/kometa -op --time 06:00
sudo docker run --restart=unless-stopped -d -v "/path/to/Kometa-folder/config:/config:rw" kometateam/kometa -ov --time 06:30
sudo docker run --restart=unless-stopped -d -v "/path/to/Kometa-folder/config:/config:rw" kometateam/kometa -co --time 08:00

Windows:
docker run --restart=unless-stopped -d -v "C:\path\to\Kometa-folder/config:/config:rw" kometateam/kometa -op --time 06:00
docker run --restart=unless-stopped -d -v "C:\path\to\Kometa-folder/config:/config:rw" kometateam/kometa -ov --time 06:30
docker run --restart=unless-stopped -d -v "C:\path\to\Kometa-folder/config:/config:rw" kometateam/kometa -co --time 08:00

Mac:
docker run --restart=unless-stopped -d -v "~/path/to/Kometa-folder/config:/config:rw" kometateam/kometa -op --time 06:00
docker run --restart=unless-stopped -d -v "~/path/to/Kometa-folder/config:/config:rw" kometateam/kometa -ov --time 06:30
docker run --restart=unless-stopped -d -v "~/path/to/Kometa-folder/config:/config:rw" kometateam/kometa -co --time 08:00
```

#### For Testing (One-time run):

```powershell
Linux: sudo docker run -it -v "/path/to/Kometa-folder/config:/config:rw" kometateam/kometa --run

Windows: docker run -it -v "C:\path\to\Kometa-folder/config:/config:rw" kometateam/kometa --run

Mac: docker run -it -v "~/path/to/Kometa-folder/config:/config:rw" kometateam/kometa --run
```

## 🔄 Updating Kometa

```powershell
Stable: docker pull kometateam/kometa
Develop: docker pull kometateam/kometa:develop
Nightly: docker pull kometateam/kometa:nightly
```

## 📋 Supported Libraries

| Library Type   | Status              |
| -------------- | ------------------- |
| 🎬 Movies      | Active              |
| 📺 TV Shows    | Active              |
| 🏮 Anime       | Active              |
| 🎵 Music       | Active              |
| 🎞️ Remux       | Active              |
| 📚 Audiobooks  | Disabled by default |
| 🎼 Soundtracks | Disabled by default |
| 🎥 Videos      | Disabled by default |

### 💾 Collections examples

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

## 📚 Documentation

For more detailed information, visit the [official Kometa wiki](https://metamanager.wiki/en/latest/).

<p align="center">
  <p>Tools and technologies:</p>
</p>

<p align="center">
  <a href="https://kometa.wiki/en/latest/" title="Kometa">
    <img src="https://cdn.jsdelivr.net/gh/selfhst/icons/png/kometa.png" width="60" height="60"></a>
  <a href="https://radarr.video" title="Radarr">
    <img src="https://cdn.jsdelivr.net/gh/selfhst/icons/svg/radarr.svg" width="60" height="60"></a>
  <a href="https://sonarr.tv" title="Sonarr">
    <img src="https://cdn.jsdelivr.net/gh/selfhst/icons/svg/sonarr.svg" width="60" height="60"></a>
  <a href="https://www.themoviedb.org/" title="TMDB">
    <img src="https://cdn.jsdelivr.net/gh/selfhst/icons/svg/tmdb.svg" width="60" height="60"></a>
  <a href="https://www.thetvdb.com" title="TVDB">
    <img src="https://cdn.jsdelivr.net/gh/selfhst/icons/svg/tvdb.svg" width="60" height="60"></a>
  <a href="https://trakt.tv/" title="Trakt">
    <img src="https://trakt.tv/assets/logos/logomark.square.gradient-b644b16c38ff775861b4b1f58c1230f6a097a2466ab33ae00445a505c33fcb91.svg" width="60" height="60"></a>
  <a href="https://www.imdb.com" title="IMDb">
    <img src="https://upload.wikimedia.org/wikipedia/commons/6/69/IMDB_Logo_2016.svg" width="60" height="60"></a>
  <a href="https://theposterdb.com" title="ThePosterDB">
    <img src="https://theposterdb.com/assets/logos/icon/color.svg" width="60" height="60"></a>
</p>
