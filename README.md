# Awesome Game Mashups

> A curated list of games rebuilt **inside other games**: cross-game mechanics, engine/runtime mashups, full-system recreations, playable ports, and technically interesting “this game has no business running in that game” projects.

![Curated](https://img.shields.io/badge/status-curated-success)
![PRs welcome](https://img.shields.io/badge/PRs-welcome-brightgreen)
![Links](https://github.com/bailo167/awesome-game-mashups/actions/workflows/links.yml/badge.svg)
![Last verified](https://img.shields.io/badge/verified-2026--10--01-blue)
![License: CC0](https://img.shields.io/badge/list%20license-CC0--1.0-lightgrey)

**Last verified:** 1 October 2026.

[**➕ Submit a game mashup**](https://github.com/bailo167/awesome-game-mashups/issues/new?template=new-project.yml) · [Browse structured data](data/projects.json) · [Contribution guide](CONTRIBUTING.md)

This list focuses on substantial cross-game work: one game's gameplay, systems, world, runtime, or mechanics being recreated or embedded in another. A themed skin pack or asset swap alone does not qualify.

## Contents

- [Legend](#legend)
- [Playable / source available](#playable--source-available)
- [Verified demos and works in progress](#verified-demos-and-works-in-progress)
- [Unverified viral watchlist](#unverified-viral-watchlist)
- [Adjacent / borderline](#adjacent--borderline)
- [Creator clusters](#creator-clusters)
- [What belongs here?](#what-belongs-here)
- [Contributing](#contributing)

## Legend

| Marker | Meaning |
|---|---|
| 🟢 | Publicly playable/downloadable |
| 🟣 | Public source available |
| 🟡 | Verified demo/WIP, but no public playable release |
| 🔴 | Viral claim or footage not independently verifiable yet |
| ⚪ | Adjacent/borderline — interesting, but not a full systems mashup |

## Playable / source available

### 2010 Rust Rewrite Mashup — *MW2 + Skate 3 + Minecraft*

**Guest:** *Skate 3*, *Minecraft*  
**Host/runtime:** *Call of Duty: Modern Warfare 2* via IW4L  
**Creator:** [chasmlol](https://github.com/chasmlol)  
**Status:** 🟢 🟣 Released, source available  
**Approach:** from-scratch Rust MW2 runtime + Skate 3 mode + Minecraft world/runtime integration

A from-scratch Rust rewrite of MW2 that combines MW2 multiplayer, Skate 3-style skating and a real generated Minecraft world. The Minecraft mode includes blocks, mobs, inventory, mining/placing and world generation; Skate mode uses data from a user-owned Xbox 360 copy.

- [Source repository](https://github.com/chasmlol/2010-rust-rewrite-mashup)
- [Releases](https://github.com/chasmlol/2010-rust-rewrite-mashup/releases)
- [IW4L upstream](https://github.com/vladtrc/iw4L)

---

### SkyCraft — *Minecraft inside Skyrim*

**Guest:** *Minecraft: Java Edition* mechanics/runtime  
**Host:** *The Elder Scrolls V: Skyrim Special Edition*  
**Creator:** [chasmlol](https://github.com/chasmlol)  
**Status:** 🟢 🟣 Early/experimental release  
**Approach:** Skyrim SKSE plugin + Minecraft Fabric mod communicating via shared memory

Minecraft remains running as the game-logic side while Skyrim renders the world. Movement, inventory, HUD, blocks, digging, fluids, lighting, combat and parts of Minecraft progression are integrated into Skyrim's world.

- [Source repository](https://github.com/chasmlol/SkyCraft)
- [Releases](https://github.com/chasmlol/SkyCraft/releases)

---

### HytaleDoom — *DOOM inside Hytale*

**Guest:** *DOOM*  
**Host:** *Hytale*  
**Creator:** [tr7zw](https://github.com/tr7zw)  
**Status:** 🟣 Source available / tech demo  
**Approach:** Java Doom implementation rendered and controlled through a Hytale mod

A deliberately rough proof-of-concept built in a few nights. DOOM is rendered as raw pixel data inside Hytale and is controlled from the game.

- [Source repository](https://github.com/tr7zw/HytaleDoom)
- [Creator video](https://www.youtube.com/watch?v=RxVj6_NKRDY)
- [vanilla-mocha-doom dependency](https://github.com/gaborbata/vanilla-mocha-doom/)

---

### Halocraft — *Minecraft-style destruction inside Halo 3*

**Guest:** *Minecraft* mechanics  
**Host:** *Halo 3* / *Halo: The Master Chief Collection*  
**Creator:** InfernoPlus  
**Status:** 🟢 Released  
**Approach:** Halo 3 multiplayer maps with destructible Minecraft-style voxel structures using Halo's physics

Four destructible Minecraft maps built inside Halo 3. This is more than a texture swap: the key technical feature is destructible block geometry in a host engine not designed for Minecraft-style terrain destruction.

- [Steam Workshop](https://steamcommunity.com/sharedfiles/filedetails/?id=2899362333)
- [Original release post](https://www.patreon.com/infernoplus/posts/halocraft-73930239)
- [Official Halo spotlight](https://www.halowaypoint.com/news/halo-mcc-modtacular-2)

---

### Dark Souls: Remastest / Remastester — *Halo inside Dark Souls*

**Guest:** *Halo* maps, weapons and multiplayer ideas  
**Host:** *Dark Souls: Prepare to Die Edition*  
**Creator:** InfernoPlus and collaborators  
**Status:** 🟢 Released  
**Approach:** extensive Dark Souls modding; Halo maps/weapons plus multiplayer overhaul

A large multiplayer-focused Dark Souls overhaul that evolved into a Halo/Dark Souls mashup, including Halo maps and weapons alongside major multiplayer and combat changes.

- [Creator video — “Dark Souls Except It's Incredibly Cursed”](https://www.youtube.com/watch?v=qRBTMhG2_00)
- [Current Remastest release post](https://www.patreon.com/infernoplus/posts/dark-souls-90413873)
- [Original release post](https://www.patreon.com/infernoplus/posts/dark-souls-46865100)
- [Community tooling: DS Gadget for Remastest](https://github.com/Nordgaren/DS-Gadget-for-Remastest)

---

### Ocarina of Time in Minecraft — *The full Zelda adventure rebuilt in Minecraft*

**Guest:** *The Legend of Zelda: Ocarina of Time*  
**Host:** *Minecraft*  
**Creator:** Rivero  
**Status:** 🟢 Released  
**Approach:** long-form Minecraft adventure-map recreation with custom systems, bosses, quests and progression

A seven-year solo recreation designed to be playable from beginning to end, covering the world, bosses, sidequests, story and items rather than only reproducing the map geometry.

- [Download / project page](https://rivero7462.itch.io/ocarina-of-time-in-minecraft)
- [Release trailer](https://www.youtube.com/watch?v=HSGioTZ_rf4)

## Verified demos and works in progress

### Minecraft voxel engine inside Super Mario 64

**Guest:** Minecraft-style voxel/world systems  
**Host:** *Super Mario 64* / Nintendo 64  
**Creator:** Arthurtilly  
**Status:** 🟡 Verified demo; unreleased  
**Approach:** custom voxel engine written inside the SM64 engine

Runs on emulator and, with reduced render distance, on original Nintendo 64 hardware. The demonstrated build has infinite terrain generation, multiple block types and biomes, early fluid support and lighting features.

- [Creator video](https://www.youtube.com/watch?v=Fo1_-UalrmY)
- [Original creator post](https://x.com/arthurtilly413/status/1924566904498487662)
- [Creator GitHub](https://github.com/arthurtilly)

---

### Morrowind in Elden Ring

**Guest:** *The Elder Scrolls III: Morrowind*  
**Host:** *Elden Ring*  
**Creator:** InfernoPlus and collaborators  
**Status:** 🟡 Verified WIP; no public build located  
**Approach:** large-scale world/asset conversion and recreation in Elden Ring's engine

An ongoing attempt to move Morrowind's world into Elden Ring. The public showcase demonstrates a substantial amount of converted world content, but it remains a work in progress rather than a finished Morrowind replacement.

- [Creator showcase](https://www.youtube.com/watch?v=n89NFtIUWDI)

## Unverified viral watchlist

These are intentionally separated from the verified list. **A real video is not the same thing as a reproducible public project.** Entries stay here until there is a primary source, release, repository, or enough technical evidence to verify what is actually running.

### “Minecraft in Elden Ring” — TobynJacobs

**Claim:** Minecraft systems/items/redstone/creative-mode style functionality running in Elden Ring.  
**Status:** 🔴 Footage exists; no public repository or download located as of 1 Oct 2026. Implementation claims remain unverified externally.

- [Original X post](https://x.com/TobynJacobs/status/2104884843297599594)
- [Independent status check](https://heldgames.com/guides/is-that-viral-mod-video-real)

---

### “Minecraft in GTA V”

**Claim:** Minecraft-like systems/gameplay combined with GTA V.  
**Status:** 🔴 Viral footage/discussion; no matching public source or release verified as of 1 Oct 2026.

- [Example discussion](https://www.reddit.com/r/GTAV/comments/1wuppva/somebody_modded_minecraft_into_gta_5/)
- [Independent status check](https://heldgames.com/guides/is-that-viral-mod-video-real)

---

### “Minecraft in Cyberpunk 2077”

**Claim:** Minecraft gameplay/systems inside Cyberpunk 2077.  
**Status:** 🔴 No matching public source/release verified as of 1 Oct 2026.

- [Independent status check](https://heldgames.com/guides/is-that-viral-mod-video-real)

---

### Earlier viral “Minecraft in Skyrim” footage

**Claim:** viral Minecraft-in-Skyrim footage circulating before SkyCraft's public release.  
**Status:** 🔴 The earlier clip itself was not independently sourced. **Do not conflate it with [SkyCraft](https://github.com/chasmlol/SkyCraft), which is a separate, now-verifiable public project.**

- [Independent status check](https://heldgames.com/guides/is-that-viral-mod-video-real)

## Adjacent / borderline

These are worth tracking, but are not treated as core cross-game/system mashups.

### Portal Zombies — *Portal-themed Black Ops III Zombies map*

**Guest/theme:** *Portal*  
**Host:** *Call of Duty: Black Ops III Zombies*  
**Creator:** xdferpc  
**Status:** ⚪ 🟢 Released  
**Why adjacent:** uses Portal textures, models and teleporters in a custom Zombies map, but does not attempt to recreate Portal's full game systems.

- [Steam Workshop](https://steamcommunity.com/sharedfiles/filedetails/?id=856630622)

## Creator clusters

### chasmlol

Currently one of the clearest sources for the 2026 wave of public, inspectable mashups.

- [2010 Rust Rewrite Mashup](https://github.com/chasmlol/2010-rust-rewrite-mashup)
- [SkyCraft](https://github.com/chasmlol/SkyCraft)
- [IW4L fork](https://github.com/chasmlol/iw4L)
- [Skate 3 preservation/recomp work](https://github.com/chasmlol/skate3-recomp)

### InfernoPlus

A long-running precursor to the current wave, with multiple technically ambitious cross-game projects.

- Halo systems/maps in Dark Souls — Remastest / Remastester
- Minecraft-style destruction in Halo 3 — Halocraft
- Morrowind world conversion into Elden Ring — WIP

## What belongs here?

A project is a good fit when it does at least one of these:

- runs one game's logic/runtime inside another game;
- recreates a substantial part of one game's mechanics inside another;
- ports/rebuilds a game's world **and** meaningful gameplay systems into a different host;
- creates a technically substantial cross-engine mashup rather than a cosmetic crossover;
- is a historically important precursor to the current scene.

Usually **not** included in the core list:

- skins or character swaps only;
- texture packs;
- one imported map with otherwise unchanged host gameplay;
- ordinary themed custom maps;
- Easter eggs;
- AI-generated/video-only claims with no verifiable implementation — these go in the watchlist instead.

## Contributing

Contributions are welcome. See [CONTRIBUTING.md](CONTRIBUTING.md), or [open the project submission form](https://github.com/bailo167/awesome-game-mashups/issues/new?template=new-project.yml).

The short version: **primary sources first**. If the only evidence is a viral repost, submit it to the watchlist instead of presenting it as verified.

Structured project metadata also lives in [`data/projects.json`](data/projects.json).

## Attribution and trademarks

Game names and trademarks belong to their respective owners. This repository is an independent community index and is not affiliated with the developers or publishers of the listed games.

The curation/metadata in this repository is dedicated to the public domain under CC0-1.0 where legally possible. Linked projects keep their own licenses and terms.
