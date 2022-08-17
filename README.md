# gzdoom

## gzdoom release

```bash
$ cd ~/games
$ mkdir -p gzdoom/releases
$ cd gzdoom/releases
$ curl -OL https://zdoom.org/files/gzdoom/bin/gzdoom-legacy_3.8.2_amd64.deb
$ curl -OL https://github.com/coelckers/gzdoom/releases/download/g4.8.2/gzdoom_4.8.2_amd64.deb
```

install

```bash
$ cat Aptfile | xargs sudo apt install -y
$ dpkg -i releases/gzdoom_4.8.2_amd64.deb
# set the location for doom wads and addons
$ export DOOMWADDIR=$HOME/games/gzdoom
```

uninstall

```bash
$ sudo apt --purge remove gzdoom gzdoom-legacy
```

configuration lives at `~/.config/gzdoom/`

fluidsynth looks for `sf2` sound font files at `/usr/share/sounds/sf2/`. Symlink files 
within this directory, or set `fluid_patchset=/path/to/sound-font.sf2` in `gzdoom.ini`.

start it up

```bash
$ gzdoom
# or edit the 'run' script, and
$ ./run
```

## addons

[moddb](https://www.moddb.com/games/doom/mods?sort=visitstotal-desc)

* idkfa-soundtrack: https://www.moddb.com/mods/brutal-doom/addons/idkfa-doom-soundtrack
* hydros-zdoom-overhaul: https://www.moddb.com/games/doom/addons/zdoom-overhaul-pack
* perkristian-high-res-sfx: https://www.perkristian.net/game_doom-sfx.shtml
* smooth-doom: https://www.doomworld.com/forum/topic/69451-smooth-doom-update-41420/
* beautiful-doom: https://github.com/jekyllgrim/Beautiful-Doom#readme
* hoover1979-ultrahd-textures: https://www.moddb.com/mods/hoover1979-ultrahd-doom-texture-pack/downloads/1k-texture-pack-3rd-demo-24052020-single-file
* x16-sprite-pack: https://www.moddb.com/mods/x16-sprite-pack-doom/downloads/x16-sprite-pack-vanilla-doom-complete-v08
* doom-sound-bulb: https://www.doomworld.com/forum/topic/110822-doom-sound-bulb-hd-sounds-that-stay-true-to-the-original/
* 300-pounds-sound-pack: https://forum.zdoom.org/viewtopic.php?f=46&t=70078
* trevor0402-sc-55-soundfont: https://github.com/trevor0402/SC55Soundfont/releases
* patch93-sc-55-soundfont: https://musical-artifacts.com/artifacts/1228
* hd-textures: https://www.youtube.com/watch?v=Zx6EoeKxMV0

## fix fluidsynth

```bash
$ ./run
fluidsynth: warning: SDL2 not initialized, SDL2 audio driver won't be usable
$ sudo apt install fluidsynth libfluidsynth-dev
```

## Beautiful-Doom

```bash
$ mkdir beautiful-doom
$ cd beautiful-doom
$ curl -OL https://github.com/jekyllgrim/Beautiful-Doom/releases/download/7.1.6/Beautiful_Doom_716.pk3
```
