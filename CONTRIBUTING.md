# Contributing

Thanks for helping keep **Awesome Game Mashups** useful.

## Before submitting

A core-list entry should involve a substantial cross-game or cross-engine implementation — not just an asset swap, skin, texture pack, ordinary themed map, or Easter egg.

Please gather at least one **primary source** where possible:

1. official source repository;
2. official release/download page;
3. creator's original video/post;
4. creator's project site or technical write-up.

Secondary reporting is useful for corroboration, but should not replace an available primary source.

## Verification states

Use the least-strong status that the evidence supports:

- `released` — public playable/downloadable build exists;
- `source-available` — public source exists;
- `verified-wip` — creator/project is verified, but no public playable release exists;
- `video-only` — primary creator footage exists, implementation is not reproducible externally;
- `unverified` — only reposts/claims exist or the underlying implementation cannot be confirmed;
- `adjacent` — interesting crossover, but does not meet the core inclusion bar.

Never turn “I saw a clip” into “this mod exists and is downloadable.”

## Submission checklist

- Project name
- Guest/source game
- Host game/runtime
- Creator
- First known public date
- Current status
- Primary URL
- Download/release URL, if any
- Source-code URL, if any
- Short description of what is actually implemented
- Technical approach, if documented
- License, if known
- AI-assistance claim only when stated by the creator or a reliable source
- Notes explaining any uncertainty

## Keeping the README easy to browse

The README has two layers: a simple project list at the top and the full project details below. Preserve both.

- Add each project once to the appropriate overview table and once to the detailed catalogue. Keep the overview to **Project | What it is | Status**, with one plain-language sentence explaining the experience, not the engineering.
- Link the overview title to the detailed entry's stable `#project-...` anchor. Keep existing anchors working when renaming a project, and include a **Back to project list** link after its details.
- Use readable statuses without strengthening the evidence. **Released**, **Early release** and **Playable** require a public playable version; **Code available** means public source, not necessarily a ready-to-play download. Keep demo-only and video-only projects clearly labelled.
- Keep unconfirmed sightings and related/borderline projects in their separate overview sections. Do not mix them into the playable list.
- Preserve the detailed descriptions, limitations, attribution and evidence links. Clearly label downloads, installation instructions, videos and source code; never label a source-only repository as a download.

When adding, renaming, reclassifying or updating a project, synchronize its overview row, detailed entry and `data/projects.json` record in the same change. Check for missing/duplicate entries, conflicting statuses and broken jump/back links. Names may use a documented alias, but must identify the same project unambiguously.

Keep badges, structured data and contributor-oriented material below the browsing experience. Do not move the full details into collapsed sections or replace them with only the summary table.

## Link verification

The README intentionally has no **Check links / Links** workflow badge. Do not restore it during maintenance.

Check primary-source and download URLs, project jump links and back links during review, regardless of whether automated checking runs. An HTTP 403 alone does not prove a link is dead; document access limitations and use other primary evidence where possible.

If automated link checking has been disabled, leave it disabled unless the maintainer explicitly requests otherwise. Do not recreate a replacement workflow or treat an intentionally disabled check as a failed or passed check. Report automated results only for runs that actually occurred; a workflow file or missing run alone does not establish its current enabled/disabled setting.

## Editing `data/projects.json`

Keep entries factual and compact. URLs should point as close to the original project as possible.

Do not infer a license. Use `null` when unknown.

Do not infer AI use from code style, posting frequency, or social-media speculation.

## Pull requests

Keep one project or one tightly related group of corrections per PR when practical. Include the sources you checked in the PR description.
