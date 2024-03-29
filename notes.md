# notes

## install dependencies

```bash
$ cat Aptfile | xargs sudo apt install -y
```

## download gzdoom releases

```bash
$ cd ~/games
$ mkdir -p gzdoom/releases
$ cd gzdoom/releases
$ curl -OL https://zdoom.org/files/gzdoom/bin/gzdoom-legacy_3.8.2_amd64.deb
$ curl -OL https://github.com/coelckers/gzdoom/releases/download/g4.8.2/gzdoom_4.8.2_amd64.deb
```

install

```bash
$ dpkg -i releases/gzdoom_4.8.2_amd64.deb
```

default configuration lives at `~/.config/gzdoom/`

start it up

```bash
$ gzdoom
# or edit the 'run' script, and
$ ./run
```

to uninstall...

```bash
$ sudo apt --purge remove gzdoom gzdoom-legacy
```

## libsdl2 error

```bash
$ sudo dpkg -i releases/gzdoom_4.8.2_amd64.deb
dpkg: dependency problems prevent configuration of gzdoom:
gzdoom depends on libsdl2-2.0-0; however:
Package libsdl2-2.0-0 is not installed.
$ sudo apt --fix-broken install libsdl2-dev
```

## no sound

```bash
$ sudo apt install libopenal-dev
```

## version control configuration

```bash
$ cp ~/.config/gzdoom/gzdoom.ini ./gzdoom.ini
# add '-config ./gzdoom.ini' to 'run' script
```

## fluidsynth with Roland SC-55 soundfonts

```bash
$ ./run
fluidsynth: warning: SDL2 not initialized, SDL2 audio driver won't be usable
$ sudo apt install fluidsynth libfluidsynth-dev
```

fluidsynth looks for `sf2` sound font files at `/usr/share/sounds/sf2/`. Symlink files 
within this directory, or set `fluid_patchset=/path/to/sound-font.sf2` in the 
`gzdoom.ini` file.

```bash
$ cd sfx
$ curl -OL https://musical-artifacts.com/artifacts/1228/SC-55.sf2
$ curl -OL https://github.com/trevor0402/SC55Soundfont/releases/download/v1.2b/SC-55.SoundFont.v1.2b.sf2
```

```
# gzdoom.ini
fluid_patchset=$HOME/games/gzdoom/sfx/SC-55.sf2 # or
# fluid_patchset=$HOME/games/gzdoom/sfx/SC-55.SoundFont.v1.2b.sf2
```

## Beautiful-Doom

[[github](https://github.com/jekyllgrim/Beautiful-Doom#readme)]

```bash
$ cd gfx
$ curl -OL https://github.com/jekyllgrim/Beautiful-Doom/releases/download/7.1.6/Beautiful_Doom_716.pk3
# add '-file ./gfx/Beautiful_Doom_716.pk3' to 'run' script
$ cd ..
$ ./run
```

## IDKFA Soundtrack

https://www.moddb.com/mods/brutal-doom/addons/idkfa-doom-soundtrack

```bash
$ cd sfx
$ mkdir idkfa-soundtrack
$ cd idkfa-soundtrack
$ mv ~/Downloads/IDKFA_Soundtrack_Mod_v2.zip .
$ unzip IDKFA_Soundtrack_Mod_v2.zip
# add '-file ./sfx/idkfa-soundtrack/WAD/IDKFAv2.wad' to 'run' script
$ cd ../..
$ ./run
```

## other addons

* [moddb](https://www.moddb.com/games/doom/mods?sort=visitstotal-desc)
* idkfa-soundtrack: https://www.moddb.com/mods/brutal-doom/addons/idkfa-doom-soundtrack
* hydros-zdoom-overhaul: https://www.moddb.com/games/doom/addons/zdoom-overhaul-pack
* perkristian-high-res-sfx: https://www.perkristian.net/game_doom-sfx.shtml
* hoover1979-ultrahd-textures: https://www.moddb.com/mods/hoover1979-ultrahd-doom-texture-pack/downloads/1k-texture-pack-3rd-demo-24052020-single-file
* x16-sprite-pack: https://www.moddb.com/mods/x16-sprite-pack-doom/downloads/x16-sprite-pack-vanilla-doom-complete-v08
* doom-sound-bulb: https://www.doomworld.com/forum/topic/110822-doom-sound-bulb-hd-sounds-that-stay-true-to-the-original/
* 300-pounds-sound-pack: https://forum.zdoom.org/viewtopic.php?f=46&t=70078
* trevor0402-sc-55-soundfont: https://github.com/trevor0402/SC55Soundfont/releases
* patch93-sc-55-soundfont: https://musical-artifacts.com/artifacts/1228
* hd-textures: https://www.youtube.com/watch?v=Zx6EoeKxMV0

## WadSmoosh

Combine iwads for official DOOM releases into one `doom_complete.pk3` file.

[[homepage](https://jp.itch.io/wadsmoosh)]

[[source code](https://heptapod.host/jp-lebreton/wadsmoosh)]
