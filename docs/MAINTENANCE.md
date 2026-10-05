# Build, publication and evidence guide

## Architecture

One project dataset (`data/projects.json`) drives the README browser and details, static website, per-project pages, Atom feed and weekly digest. `data/site.json` controls the editorial date and featured IDs. Counts distinguish core, watchlist and related entries. The site is dependency-free HTML/CSS/JavaScript; building and unit tests require Python 3.12+ only. Browser testing has separate pinned development dependencies.

`id` keeps existing README anchors and site permalinks stable. `first_seen` describes the project's history; `added_at` describes this index's history. Migration recovers catalogue addition dates from full Git history, rather than inventing them. Inherited metadata is preserved, and inherited source-review dates remain unknown until someone reviews the source.

`python3 scripts/catalogue.py build` regenerates outputs. `check` rejects stale committed README/digest output. `validate` checks semantic constraints. The editor schema documents field types; Python additionally checks duplicate records and evidence/availability contradictions.

## Publishing the site

The code and downloadable build are useful before hosting is enabled. **Do not announce a live Pages URL until deployment succeeds.**

The repository owner selects **Settings → Pages → Build and deployment → Source → GitHub Actions**. Then run **Actions → Catalogue integrity → Run workflow**, on `main`. The workflow packages `_site` and deploys only when repository metadata confirms Pages has been enabled. No custom personal access token is needed for ordinary deployments after owner setup.

Intended address: `https://bailo167.github.io/awesome-game-mashups/`. Confirm home, a project permalink, assets, `feed.xml` and `build-info.json`. Only after this readback should `data/site.json` set `site_enabled: true`, followed by regeneration; this controls the README live-site call to action.

Pages enablement is administrative. Committing files does not imply permission to enable Pages. The workflow never tries to bypass that boundary. If enablement is blocked, retain the build artifact and report the owner action.

## Workflows

- **Catalogue integrity:** PRs get read-only validation, unit tests and generated-output checks. Trusted `main` runs can migrate the legacy schema and regenerate committed outputs in a normal non-force-pushed commit. Artifacts record the resulting source commit. A separate read-only Chromium browser job tests HTTP search/filters, URL persistence, mobile layout and no-JavaScript fallback before main-only Pages deployment.
- **Check links:** public reachability audit with no auth headers. Redirect destinations are validated. 2xx = reachable; 404/410 = unavailable; 403/429/timeouts = unresolved. HTTP success does not verify claims. The JSON report retains unresolved URLs rather than hiding them with broad exceptions.
- Action references are pinned to verified full commit SHAs. Dependabot proposes updates; nothing auto-merges dependency or workflow changes.

Public PR code never runs with a write token, `pull_request_target`, or a private-network runner. Require review for workflows and generators when enabling branch rules; CODEOWNERS alone is review routing.

## Audit findings addressed

The previous README had blank-line breaks inside three tables. Metadata and prose were independently maintained. Demo fields were underused. A global “Last verified” badge obscured per-project uncertainty. The old link checker accepted rate-limit responses as successful checks.

The new implementation generates all views together, surfaces existing demo links, records source-review scope separately from play-testing, and separates reachability from verification. All inherited entries remain present; this structural upgrade does not pretend to re-test every game.

## Research basis, checked 5 October 2026

- [GitHub: custom Pages workflows](https://docs.github.com/en/pages/getting-started-with-github-pages/using-custom-workflows-with-github-pages): owner enablement, artifacts, deployment dependencies, Pages/OIDC permissions and environments.
- [GitHub: secure workflow use](https://docs.github.com/en/actions/reference/security/secure-use): least privilege, SHA pinning, untrusted PR isolation, CODEOWNERS and Dependabot.
- [W3C WCAG 2.2 reference](https://www.w3.org/WAI/WCAG22/quickref/): keyboard access, visible focus, readable contrast, target sizes and reduced motion. Design guidance, not certification of full WCAG compliance.
- [JSON Schema reference](https://json-schema.org/understanding-json-schema/reference/type): documented record types and machine-readable constraints.
- [Official Awesome submission checklist](https://github.com/sindresorhus/awesome/blob/main/pull_request_template.md): do not promise admission after 30 days. The checklist currently rejects AI-generated material and generated READMEs. This is an independent AI-assisted catalogue, not an official-directory endorsement.

## Completion and checkpoints

A local build, unmerged branch or successful HTTP request is not completion. Publish intended changes to main, read them back, inspect final Actions and record what they checked. Preserve the last genuinely completed research-cycle checkpoint during a structural upgrade or partial recheck. Record a separate structural-upgrade checkpoint instead of rewriting history.

Scheduled research should prioritize missing demos, undocumented requirements, stale reviews and unresolved links, not just project counts.
