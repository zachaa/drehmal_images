# Image Files for Drehmal Map
## `maps`
Map Tiles generated with **[uNmINeD](https://unmined.net/)**

### Export Options in uNmINeD
Snap to: Regions
Format: PNG
Background: `#000000`

1. **Overworld**
    - x: -6144, 28159
    - z: -5632, 8191
    - 2(4:1) → -6(1:64)
    - Include 4 regions of Mt. Yavhlix interior with X-Ray hide above: **132**
        - x: 26624, 27135
        - z: -512, -1
        - make sure Update changed regions only is unchecked for this part
2. **Lo'Dahr**
    - x: -2560, 2559
    - z: -3072, 2559
    - zoom: 2(4:1) → -6(1:64)
    - Include 4 regions of The Core with X-Ray hide above: **129**
        - x: 26624, 27135
        - z: -512, -1
3. **Space**
    - x: -512, 511
    - z: -512, 511
    - zoom: 2(4:1) → -2(1:4)
4. **End**
    - x: -512, 511
    - z: -512, 511
    - zoom: 2(4:1) → -2(1:4)
5. **True End**
    - x: -512, 10751
    - z: -1024, 10751
    - zoom: 2(4:1) → -4(1:16)

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

Update this repo by removing the old files from history before adding the new ones. Do this to not waste space.

1. Use `git filter-repo --path maps --invert-paths` to remove the files.

2. Clean up git:<br>
`git reflog expire --all --expire=now`<br>
`git gc --prune=now --aggressive`
4. Update remote<br>
`git push origin --force --all`
5. Add in the new map files and commit like normal.
    - Make sure to add a `null_tile.webp` to the `\maps` directory
6. Update the main map repo.

## `icons`
Icons from Minecraft Java Edition 1.21, Drehmal Resource Pack, Minecraft Wiki.
Some images were taken in game then saved, such as the Mythical weapons.