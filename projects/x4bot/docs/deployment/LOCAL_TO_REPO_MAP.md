# Local-to-Repository Mapping

This map prevents the Windows working directory from being copied into Git as-is.

| Local content type | Repository destination | Notes |
|---|---|---|
| Production Python modules | `projects/x4bot/src/<component>/` | Refactor only after framework review |
| Read-only diagnostics | `projects/x4bot/scripts/diagnostics/` | No runtime output committed |
| State migrations | `projects/x4bot/scripts/migrations/` | Must include backup and rollback |
| Scheduled-task entry scripts | `projects/x4bot/scripts/scheduled-tasks/` | Task XML goes under `deploy/task-templates/` |
| Automated tests | `projects/x4bot/tests/` | Use synthetic or redacted fixtures |
| Safe config examples | `projects/x4bot/config/` | Use `.example` filenames |
| Project-specific tools | `projects/x4bot/tools/` | No embedded environments or caches |
| Architecture documents | `projects/x4bot/docs/architecture/` | Stable designs only |
| Operational runbooks | `projects/x4bot/docs/operations/` | Verified procedures only |
| Device migration material | `projects/x4bot/deploy/` and `docs/deployment/` | Scripts and guides separated |
| GPT/Mimo continuity material | `projects/x4bot/docs/handoff/` | ChatGPT-controlled summaries |
| Version and checksum data | `projects/x4bot/manifests/` | No runtime state |
| Logs, databases, chat archives, mutable state | Not committed | Remain on the host or secure backup |

Mimo must report a proposed mapping before any large move. ChatGPT approves the final destination paths.
