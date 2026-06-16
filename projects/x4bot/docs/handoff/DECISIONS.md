# Decisions

## D-001 Externalized continuity

Critical project context must live in GitHub, Linear, and Gmail rather than a single chat history.

## D-002 Framework ownership

ChatGPT owns repository structure, project manifests, handoff format, and acceptance criteria. Mimo implements only within approved paths.

## D-003 Runtime separation

Logs, databases, chat archives, credentials, and mutable state remain outside Git.

## D-004 Email bridge

Mimo and ChatGPT exchange structured reports through the X4BRIDGE email convention. Local polling may download mail without invoking a model.

## D-005 Watchdog safety

Automatic recovery remains disabled until exact-process targeting and controlled recovery tests are complete.

## D-006 WatchScan evidence

No-reply results are not trusted when the data source does not include bot outbound messages.
