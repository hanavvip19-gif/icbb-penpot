# Penpot Fork Context

Read this file before changing Penpot source. `CLAUDE.md` is the V2 context
adapter and points here. The existing root `AGENTS.md` is vendor-provided,
tracked, and intentionally preserved; do not replace, rename, or edit it.

## Project

This repository is the ICBB development fork of Penpot. It contains vendor
source for product customization, not the existing deployment/runtime setup.
The operations repository remains at `/home/usman/projects/platform/penpot`.

## Repository Topology

- `origin`: `git@github.com:hanavvip19-gif/icbb-penpot.git`
- `upstream`: `https://github.com/penpot/penpot.git` (fetch-only)
- vendor branch: `develop`
- customization branch: `icbb/penpot`
- initial vendor baseline: `2ce202c7d85afc524829e3b666a44dffa8d51f13`
- metadata manifest: `.ai/repository.json`
- verification profile: `.ai/verification-profile.json`

Keep changes on customization or feature branches. Upstream sync must use a
pre-sync checkpoint, an isolated sync branch, conflict review, verification,
tests, and explicit human approval. Never push to `upstream`.

## Metadata Boundary

`PROJECT_CONTEXT.md`, `WORKSTATE.md`, `.ai/`, and `docs/icbb/plans/` are
versioned V2 metadata. `.agents/checkpoints/` and `.generated/` are local or
generated except for their `.gitkeep` markers. Do not spread V2 metadata into
Penpot source directories or copy runtime instructions from the operations
repository into this fork.

## Verification

Use `.ai/verification-profile.json` as the repository-specific verification
contract. Shared V2 tooling is maintained by `ai-dev-ecosystem` and is not
assumed to be installed in this source tree until the pilot activates it.
Initialize verification as NOT RUN rather than treating fork creation as a
source verification result.

## Durable Hazards

- Root `AGENTS.md` is a preserved vendor adapter, not a V2 symlink.
- The live upstream `develop` branch may advance beyond the fork baseline;
  update `last_synced_sha` only after a reviewed and verified sync.
