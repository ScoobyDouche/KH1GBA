# KH1GBA

**Kingdom Hearts 1 demake for Game Boy Advance**

This is a fork of [Pheenoh/khcom](https://github.com/Pheenoh/khcom) (the matching decompilation of *Kingdom Hearts: Chain of Memories* for GBA).  
The goal is to turn it into a full demake of *Kingdom Hearts 1* running on the Game Boy Advance.

> [!IMPORTANT]
> This repository does **not** contain any game assets or ROMs.  
> You still need a legally dumped copy of *Kingdom Hearts: Chain of Memories* (GBA) to build and extract assets.

## Current Status
- ✅ Base: 100% matching CoM decompilation (engine, battle, maps, events, etc.)
- 🚧 Project just started – no KH1-specific changes yet
- Planned direction: Keep (or adapt) the card combat system, replace maps/story/assets with a compressed KH1 experience, or experiment with simplified real-time combat on top of this engine.

## Building (same as original decomp)

### Dependencies
- git
- ninja
- python3 + PyYAML (`python3 -m pip install pyyaml`)
- `binutils-arm-none-eabi`
- [agbcc](https://github.com/pret/agbcc):

```sh
git clone https://github.com/pret/agbcc
cd agbcc && ./build.sh && ./install.sh ../khcom   # or ../KH1GBA if you rename the folder
```

### Steps
1. Clone this repo:
   ```sh
   git clone https://github.com/ScoobyDouche/khcom.git KH1GBA
   cd KH1GBA
   ```
2. Place your legally dumped CoM ROM(s) in `roms/` as `B8CE.gba` (US), `B8CJ.gba` (JP), or `B8CP.gba` (EU).
3. Extract assets:
   ```sh
   python3 tools/extract_assets.py
   ```
4. Configure:
   ```sh
   python3 configure.py
   ```
5. Build:
   ```sh
   ninja
   ```

## License
The decompilation source is under [CC0 1.0 Universal](LICENSE.md).  
All Kingdom Hearts / Disney / Square Enix intellectual property remains the property of their respective owners. This is an unofficial fan project.

## Credits
- Original CoM decomp: [Pheenoh](https://github.com/Pheenoh/khcom)
- This fork / KH1GBA demake idea: starting here

---
*Let’s make Kingdom Hearts 1 run on GBA.*
