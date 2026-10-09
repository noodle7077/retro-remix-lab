# Retro Remix Lab

A static, browser-only NES/SNES ROM remix tool. Load your own cartridge, choose a seed and effects, and download a modified ROM. No ROM is uploaded or distributed with this project.

## GitHub Pages

Publish the files in this folder to a GitHub repository. In **Settings → Pages**, choose **Deploy from a branch**, then **main** and **/(root)** and save. GitHub displays the live URL there once deployment completes.

Official instructions: https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site

## Run locally

Open `index.html` in a modern browser, or serve this folder with `python -m http.server 8765`. No dependencies or build step are needed. The worker source and game catalogue are embedded in the HTML.

## What is implemented

- Original USA Super Mario World: dedicated stage, enemy, item, boss and palette randomization.
- Valid iNES/NES 2.0 cartridges with CHR ROM: tile effects that preserve the program ROM.
- Castlevania USA / Rev 1: a graphics profile.
- Super Mario All-Stars original USA: selected palettes and raw tile effects for SMB1, Lost Levels and SMB2; SMB3 palettes only. Other regions/revisions use the experimental engine.
- Other valid NES/SNES ROMs: universal experimental corruption. A checkbox also selects this engine for known profiles.
- Experimental controls: seeded bit flips, addition, random byte replacement or swapping; 1/8/32-byte bursts; a percentage range; strength from 0–100.

Experimental corruption may crash or break games. Headers/reset vectors are protected, but changes can still hit program code or compressed data. A modified byte count does not prove visible changes or playability. Use a fresh save and test every generated ROM. There is no dedicated gameplay randomizer for every game in the catalogue.

## Sources and licenses

The embedded SMW engine derives from https://github.com/authorblues/smwrandomizer (authorblues + kaizoman666), MIT; see LICENSE.txt. All-Stars graphics ranges were identified using https://github.com/bonimy/SMAS-Disassembly. The catalogue is a simplified title extraction retrieved October 9, 2026 from https://en.wikipedia.org/wiki/List_of_Super_Nintendo_Entertainment_System_games and https://en.wikipedia.org/wiki/List_of_Nintendo_Entertainment_System_games, attributed under CC BY-SA 4.0 (https://creativecommons.org/licenses/by-sa/4.0/). The catalogue is not a compatibility test list.

Corruption controls were inspired by https://github.com/redscientistlabs/RTCV and https://github.com/Rikerz/VRC. Their code is not bundled; this implementation changes ROM files, rather than running real-time emulator memory corruption.
