# Local Workspace Layout

The current Windows runtime workspace is `%USERPROFILE%\Documents\Bot`.

This directory is a live installation, not a clean Git checkout. It must not be mirrored into Git as-is.

## Observed top-level items

- `AgentBridge/`
- `AstrBot/`
- `logs/`
- `NapCat/`
- `reports/`
- `scripts/`
- `temp_restore/`
- `tmp/`
- `tools/`
- `记录/`
- `记录器/`
- `审计打包/`
- `知识库/`
- root-level Markdown, Python, lock, state, and archive files

## Classification

### Runtime-only

These remain on the host and are not copied into Git:

- `AgentBridge/` runtime mailboxes and state
- `logs/`
- `reports/` generated output
- `temp_restore/`
- `tmp/`
- `记录/` chat archives
- `审计打包/`
- `知识库/` databases and live data
- lock files and state files
- large local backup archives

### Third-party runtime

Do not commit complete vendor/runtime trees:

- `AstrBot/`
- `NapCat/`
- environments and caches under `tools/`

Git should contain only version manifests, safe wrappers, config templates, custom code, and deployment instructions for these components.

### Source candidates

Review and map individual files instead of copying whole folders:

- `scripts/`
- `记录器/`
- safe custom code under `AstrBot/`
- root-level Python utilities
- verified root-level Markdown documentation

## Recommended separation

```text
%USERPROFILE%\Documents\Bot          # live runtime instance
%USERPROFILE%\Documents\X4Workspace  # clean Git checkout
%USERPROFILE%\Documents\X4Artifacts  # generated deployment packages
```

The live runtime path remains stable so scheduled tasks and integrations do not break. Source is curated into the Git checkout. Deployment packages are generated from the checkout plus safe manifests, never by zipping the full runtime folder.

## Migration policy

1. Do not move or rename live directories during active operation.
2. Inventory candidate files first.
3. Create a local-to-repository mapping.
4. Copy safe source into the clean checkout.
5. Run a sensitive-data scan.
6. Review the diff.
7. Commit only after ChatGPT framework approval.
8. Leave runtime data in place.
