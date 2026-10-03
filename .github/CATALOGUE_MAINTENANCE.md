# Catalogue Maintenance Contract

This file is the durable operating contract for automated maintenance of **Awesome Game Mashups**.

The live repository is always the source of truth. A previous chat report, recovery file, scheduled-task message, or remembered project count is only a lead until checked against current `main`.

## Completion standard

A maintenance run is complete only when justified changes are **published to the default branch and read back from GitHub**.

Use exactly one of these outcomes in the final report:

- `COMPLETE — PUBLISHED AND VERIFIED`
- `COMPLETE — VERIFIED NO CHANGES REQUIRED`
- `PARTIAL — SOME CHANGES PUBLISHED; WORK REMAINS`
- `BLOCKED — REQUIRED GITHUB PUBLICATION NOT COMPLETED`

Research finished, a local patch, a prepared payload, an unmerged branch, or one successful commit while other justified changes remain unpublished is not completion.

## Start-of-run procedure

1. Read live `main`, including at minimum:
   - `README.md`
   - `data/projects.json`
   - `CONTRIBUTING.md`
   - `.github/CATALOGUE_MAINTENANCE.md`
   - `.github/catalogue-state.json`
   - `.github/ISSUE_TEMPLATE/`
   - `.github/pull_request_template.md`
   - `.github/workflows/`
   - `LICENSE`
2. Read repository metadata, recent commits, open issues, open PRs, and recent Actions runs.
3. Confirm the authenticated GitHub connection can write to the repository.
4. Treat `.github/catalogue-state.json` as a checkpoint, not authority over live files. Reconcile it with `main` before using it.

Do not create dummy commits, test files, bootstrap workflows, or repository clutter just to test write access.

## Research and verification

Search broadly for newly released, announced, demonstrated, open-sourced, substantially updated, or rediscovered game-inside-game, cross-game, runtime, recompilation, decompilation, source-port, emulator, systems-mashup, and mechanics-recreation projects.

Do not limit discovery to Minecraft. Search primary repositories and forges, creator/project sites, Steam Workshop, Nexus Mods, ModDB, itch.io, YouTube, Reddit, X/Twitter, Bluesky, Mastodon where relevant, Patreon, official modding forums, game-specific communities, reverse-engineering/recompilation communities, technical blogs, reputable reporting, Hacker News, and references/credits in known projects.

Useful search patterns include:
- `X in Y`
- `X inside Y`
- `X running inside Y`
- `X recreated/rebuilt/ported to Y`
- `X mechanics/gameplay/engine in Y`
- `game inside a game`
- `cross-game mod`
- `runtime rewrite`
- `recomp mod`
- `decomp mod`
- `source port`
- `voxel engine inside`

Prefer evidence in this order:
1. official source repository;
2. official release/download page;
3. creator project page;
4. creator video/post;
5. technical documentation;
6. reputable secondary corroboration.

Re-check existing entries for new releases, source publication, repository deletion/archive, new install methods/platforms/features, creator clarifications, licence changes, renames/moves, dead links, new downloads, and status changes.

Use the least-strong supported status. Never invent metadata, licences, AI usage, creators, release availability, or technical claims. Record AI assistance only when explicitly documented by a creator or reliable primary source.

## Inclusion standard

Core entries require substantial runtime, gameplay, systems, mechanics, emulator, or world functionality recreated or embedded in another game/runtime.

Do not treat these as core by themselves:
- skins/model swaps;
- texture packs;
- ordinary map imports;
- single themed maps;
- Easter eggs;
- weapon/cosmetic packs;
- fan art;
- unverified or AI-generated-looking footage.

Use **Related / Adjacent** when technically interesting but below the core systems threshold. Keep viral claims and creator footage without reproducible evidence in **Unconfirmed sightings** / watchlist.

Distinguish:
- creator vs repost;
- original project vs fork/mirror;
- source repository vs release/download;
- source-only vs playable now;
- demonstrated functionality vs claimed functionality;
- active project vs archived historical precursor.

## Required project metadata

For each project, capture when evidence permits:
- project name and aliases;
- guest/source game;
- host game/runtime;
- creator(s);
- first public date;
- most recent activity;
- status and category;
- primary URL;
- source repository;
- release/download;
- creator video/demo;
- project page;
- platforms;
- licence;
- open-source/source availability;
- whether playable now;
- what is actually implemented;
- technical approach;
- whether original game files/ownership are required;
- runtime-downloaded assets if documented;
- explicitly documented AI assistance;
- verification notes and uncertainty.

## README presentation contract

Preserve the beginner-friendly browse-first layout.

The top catalogue is split into:
- **Available to play**
- **Code, demos and projects in development**
- **Unconfirmed sightings**
- **Related projects**

Each overview table must contain exactly:

`Project | What it is | Status`

Use one short plain-language sentence. The title links to a stable `#project-...` detail anchor.

Keep the full detailed entries below the overview. Clearly distinguish download/release links, source code, installation instructions, project pages and creator videos. Source code is not automatically a playable download.

Every detailed catalogue entry must retain a **Back to project list** link.

The old **Check links / Links** README badge is intentionally absent. Do not restore it.

## Three-way synchronization

For every project addition, removal, rename, category change, or status change, update in the same published catalogue batch:

1. the README overview row;
2. the README detailed entry;
3. `data/projects.json`.

Before publication verify:
- valid JSON;
- no duplicate project names;
- exactly one appropriate overview row per project;
- exactly one detailed catalogue entry per project;
- overview/detail/data status and category agreement;
- unique detail anchors;
- every overview jump target exists;
- every detailed entry has a back link.

Do not hard-code project counts in instructions. Derive counts from live data.

## Issues and pull requests

Review every open issue and PR on every run.

For issues:
- independently verify submissions/corrections;
- compare against existing entries;
- identify duplicates;
- apply appropriate existing labels;
- update the catalogue when justified;
- comment concisely and close resolved/invalid/duplicate issues;
- leave legitimate unresolved items open.

For PRs:
- read the full diff and evidence;
- independently verify projects;
- check duplication, JSON validity, README synchronization, status strength, licence/AI claims, URLs and contribution rules;
- merge correct contributions when permissions allow, preferring squash for simple catalogue contributions;
- request specific changes when material problems remain;
- close cleanly if a PR is superseded by already-applied work.

## Publication strategy

Do not leave all writes until the end.

Work in small coherent batches. A normal catalogue batch should contain at most about **5–10 newly added projects** plus directly related corrections. Validate and publish that batch before continuing discovery.

For catalogue changes, prefer an atomic Git commit containing synchronized README + JSON changes. Use separate focused commits for workflow/link maintenance and unrelated repository hygiene.

Before every later write:
- refresh remote `main`;
- ensure the parent is current;
- handle ordinary conflicts without overwriting unrelated changes;
- never force-push.

## Post-commit loop

After every publication batch:

1. confirm the commit SHA and target branch;
2. read changed files back from GitHub;
3. inspect the diff;
4. validate README/JSON synchronization again;
5. inspect applicable Actions runs;
6. fix actionable failures and publish the correction;
7. repeat until the current remote head is internally consistent.

A failed automated link check must be investigated. Do not assume HTTP 403 means dead. Narrowly exclude only URLs independently verified as live but bot-blocking. Never globally accept 403 or disable checking merely to obtain green CI.

If a workflow is intentionally disabled or absent, do not recreate or enable it just to satisfy an old report.

## Failure policy

A single publication failure must **not disable the scheduled audit**.

For transient GitHub/tool errors:
- refresh remote state;
- make bounded retries where appropriate;
- use another already-authorized supported GitHub write method only for ordinary technical failures;
- never bypass safety denials, branch protection, permissions, authentication, or other controls.

If publication remains blocked:
- report the exact operation that failed;
- quote the actual safe error/status;
- say what troubleshooting was attempted;
- state exactly what reached GitHub and what did not;
- preserve recoverable validated work when possible;
- leave the schedule enabled so the next scheduled run retries from live `main`.

Do not automatically disable the schedule after one, two, or three blocked runs. Human intervention should decide whether to pause recurring maintenance.

## State checkpoint

`.github/catalogue-state.json` is updated **only after a successful completed maintenance cycle**.

It records the last successful verified head and useful deduplication/checkpoint metadata. Do not advance it for partial or blocked runs.

Never let the state file override contradictory live repository contents.

## Repository hygiene

Audit description, topics, README clarity, structured data, contribution guidance, templates, labels, workflows, licence detection and enabled GitHub features.

Preferred generic topics include:
- `awesome-list`
- `game-modding`
- `mods`
- `game-mashups`
- `game-development`
- `reverse-engineering`
- `game-engine`
- `source-port`
- `recompilation`
- `decompilation`

Do not add bureaucracy such as a roadmap, wiki, Pages, SECURITY.md, or changelog unless there is a concrete need.

## Final verification

Before declaring a run complete, confirm from remote GitHub:
- final `main` SHA;
- intended files are present on default branch;
- JSON is valid;
- no duplicate catalogue entries;
- README overview/details/data agree;
- internal navigation is valid;
- issue/PR outcomes are correct;
- applicable Actions results are known;
- no temporary/debug/bootstrap artifacts remain;
- `.github/catalogue-state.json` reflects the completed head/cycle.

The repository, not the report, is the deliverable.
