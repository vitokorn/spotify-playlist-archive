# spotify-playlist-archive [![Build Status](https://api.travis-ci.com/vitokorn/spotify-playlist-archive.svg?branch=master)](https://travis-ci.com/github/vitokorn/spotify-playlist-archive)

> Daily snapshots of public Spotify playlists

Spotify's playlists are great. I like that they're updated once in a while -
change is good! I don't like, however, that it's impossible to see older
versions. How am I supposed to remember the name of that song I really liked?
Apparently, I'm not alone: see
[here](https://community.spotify.com/t5/Content-Questions/View-previous-versions-of-playlists/td-p/4400750),
[here](https://community.spotify.com/t5/Accounts/A-playlist-was-modified-Can-I-get-the-old-songs-back/td-p/1001889),
[here](https://community.spotify.com/t5/Content-Questions/Seeing-an-old-version-of-a-playlist/td-p/1318739),
[here](https://community.spotify.com/t5/Other-Partners-Web-Player-etc/Playlists-Is-there-any-way-to-recover-previous-versions-of-a/td-p/4726831),
[here](https://community.spotify.com/t5/Desktop-Mac/Find-Songs-of-old-versions-of-Spotify-Playlists/td-p/998504),
[here](https://community.spotify.com/t5/Closed-Ideas/Playlist-Versioning-History/idi-p/1133819),
[here](https://community.spotify.com/t5/Closed-Ideas/Playlist-History-Versioning/idi-p/1346418),
[here](https://community.spotify.com/t5/Closed-Ideas/Playlists-Playlist-History/idi-p/1816799),
and [here](https://community.spotify.com/t5/Live-Ideas/Playlists-Edit-History/idi-p/4573743).
Since Spotify won't take snapshots of our favorite playlists, let's do it ourselves!

## Quick start

1. To view the current version of a playlist, click on its name below
1. To see all songs that ever belonged to a playlist, click "cumulative"
1. To determine which songs were added or removed from a playlist, click "githistory"
1. To add a playlist to the archive, simply `touch playlists/plain/<playlist_id>` and make a pull request

## How it works

This repository contains a script for scraping Spotify playlists and publishing
them back to the repo. The script is run daily via
[Travis CI](https://travis-ci.com/github/vitokorn/spotify-playlist-archive)
(free for public GitHub repos). It's also run after every commit, which means
that playlists get regenerated whenever the scraping or formatting logic
changes, or when new playlists are added - cool!

The script determines which playlists to scrape by looking at the file names in
`playlists/plain`. Anything that's not a valid playlist ID gets removed. Files
that *are* a valid playlist IDs get regenerated: a pretty version of each
playlist gets dumped in `playlists/pretty`, new tracks are added to the
files in `playlists/cumulative`, and a plaintext version of each playlist is
written back to `playlists/plain`. The plain version is sorted alphabetically,
rather than by track number, so that it only changes when tracks are added or
removed, making [Git History](https://githistory.xyz/) a nice way to visualize
how the playlist evolves over time.

## Development

This project uses [`pip-tools`](https://github.com/jazzband/pip-tools) to manage
dependencies.

To get started, first create and activate a new virtual environment:
```
$ python3.8 -m venv venv
$ source venv/bin/activate
```

Then install `pip-tools`:
```
$ pip install pip-tools
```

Lastly, use `pip-sync` to install the dev requirements:
```
$ pip-sync requirements/requirements-dev.txt
```

The list below is autogenerated.

## Playlists

- [#ThrowbackThursday](https://github.com/vitokorn/spotify-playlist-archive/blob/master/playlists/pretty/#ThrowbackThursday.md)
- [Calvin Harris Guest List](https://github.com/vitokorn/spotify-playlist-archive/blob/master/playlists/pretty/Calvin%20Harris%20Guest%20List.md)
- [Coffee Club](https://github.com/vitokorn/spotify-playlist-archive/blob/master/playlists/pretty/Coffee%20Club.md)
- [Daily Mix 6](https://github.com/vitokorn/spotify-playlist-archive/blob/master/playlists/pretty/Daily%20Mix%206.md)
- [Dance Party](https://github.com/vitokorn/spotify-playlist-archive/blob/master/playlists/pretty/Dance%20Party.md)
- [Discover Weekly](https://github.com/vitokorn/spotify-playlist-archive/blob/master/playlists/pretty/Discover%20Weekly.md)
- [Fresh Finds: Basement by Spotify](https://github.com/vitokorn/spotify-playlist-archive/blob/master/playlists/pretty/Fresh%20Finds:%20Basement%20by%20Spotify.md)
- [Fresh Finds: Basement](https://github.com/vitokorn/spotify-playlist-archive/blob/master/playlists/pretty/Fresh%20Finds:%20Basement.md)
- [golden hour](https://github.com/vitokorn/spotify-playlist-archive/blob/master/playlists/pretty/golden%20hour.md)
- [Groove Theory](https://github.com/vitokorn/spotify-playlist-archive/blob/master/playlists/pretty/Groove%20Theory.md)
- [Noises After Dark](https://github.com/vitokorn/spotify-playlist-archive/blob/master/playlists/pretty/Noises%20After%20Dark.md)
- [Release Radar](https://github.com/vitokorn/spotify-playlist-archive/blob/master/playlists/pretty/Release%20Radar.md)
- [RetroWave \ Outrun](https://github.com/vitokorn/spotify-playlist-archive/blob/master/playlists/pretty/RetroWave%20\%20Outrun.md)
- [SLAP!](https://github.com/vitokorn/spotify-playlist-archive/blob/master/playlists/pretty/SLAP!.md)
- [The Wind Down](https://github.com/vitokorn/spotify-playlist-archive/blob/master/playlists/pretty/The%20Wind%20Down.md)
- [Vaporwave](https://github.com/vitokorn/spotify-playlist-archive/blob/master/playlists/pretty/Vaporwave.md)
- [Vibra Tropical](https://github.com/vitokorn/spotify-playlist-archive/blob/master/playlists/pretty/Vibra%20Tropical.md)
