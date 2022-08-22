# gzdoom

This repository contains:

- gzdoom configuration
- folder template for organizing wads/addons
- `run` script launcher

## usage

Search [`best doom wads site:reddit.com`](https://www.google.com/search?q=best+doom+wads+site%3Areddit.com), to find recommendations.

Search [`wad-name site:doomworld.com`](https://www.google.com/search?q=tnt+revilution+site%3Adoomworld.com), to find a download link.

```bash
$ cd wads
$ curl -OL https://www.gamers.org/pub/idgames/levels/doom2/megawads/tntr.zip
$ unzip tntr.zip
# add '-file ./wads/TNTR.wad -deh ./wads/TNTR.deh' to 'run' script
$ cd ..
$ ./run
```