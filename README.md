# KHRECOM-DOCUMENTATION

Where the data of Kingdom Hearts Re:Chain of Memories (PC) is, for everything KHRECOM-LUA-LIBRARY and KHRECOM-RANDOMIZER
change. One CSV per table and one row per value, in the same style as KH1-DOCUMENTATION.

## Columns

| Column | Meaning |
| --- | --- |
| `File` | Path inside the game's extracted `Recom` folder. |
| `Sub-File` | Name of the file inside that archive. |
| `Offset` | Hex offset from the start of `File`. Use it to edit the file on disk. |
| `Sub-File Offset` | Hex offset from the start of `Sub-File`. Use it on the copy the game has loaded in memory. |
| `EGS Address`, `Steam Address` | Hex address relative to the start of the exe. |
| `Value (HEX)` | The vanilla bytes, in the order they are stored. |
| `???` | Not known. |

Loaded `.ESD` and `.ABC` files keep their whole `File` in memory under its own name, so use `Offset` there (pools 18 and 37).
For every other file use `Sub-File Offset`. The pools are in `data/memory/values.csv`.

## Tables

| Folder | What is in it |
| --- | --- |
| `data/cards` | Card and sleight power, card CP, the new game deck. |
| `data/drops` | Chest, object and map card lists, their values, and the object card chances and limits. |
| `data/enemies` | HP, attack power, EXP, decks and card drop chances, and which enemy is in every field, battle and boss record. |
| `data/exe` | Rewards and tables in the exe, the enemies each room loads, and every code change the library makes. |
| `data/floors` | Floor layouts, rooms, doors and story door requirements. |
| `data/memory` | Values the library reads or writes in memory. |
| `data/moogle` | Moogle pack prices, cards and values, and the packs each floor sells. |
| `data/scenes` | Cards, sleights, battle prizes, friends and abilities given by story scripts. |
| `data/lookup` | Ids of cards, sleights, enemies, worlds and map card rooms. |

`data/scenes/scene-friends.csv` and `data/scenes/scene-movement-abilities.csv` are for reference. The library changes those
two values in memory, not in the scripts.

The file values are from the EGS version. The exe values were read from both exes.
