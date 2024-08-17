# Image Files for Drehmal Map
## `maps`
Map Tiles generated with **[uNmINeD](https://unmined.net/)**

Five different maps with zoom levels from 2 -> -2 to -6.

### Tile processing
Files were extracted as PNGs and moved to have all zoom levels for a single dimension in one folder
then compressed with [`oxipng`](https://github.com/shssoichiro/oxipng)
using the command in Python.
```cmd
{oxipng_path} -o 6 --strip safe --alpha --recursive {path}
```

- Before: 80,248 files = 1.01GB / 1.20GB
- After:  80,248 files = 539MB / 759MB

WEBP and JPG were not used even though they were significantly smaller because
they do not provide the quality needed when zoomed far in.

## `icons`
Icons from Minecraft Java Edition 1.21, Drehmal Resource Pack, Minecraft Wiki.
Some images were taken in game then saved, such as the Mythical weapons.