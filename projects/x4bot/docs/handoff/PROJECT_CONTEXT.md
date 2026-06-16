# Project Context

## Purpose

X4Bot is a Windows-hosted QQ bot operations project built around AstrBot, NapCat, WatchScan, Watchdog, Scrapling MCP, and an email-based AgentBridge between Mimo and ChatGPT.

## Roles

- User: final approval authority
- ChatGPT: framework owner, reviewer, project coordinator
- Mimo: local implementation and verification agent

## External systems

- GitHub: code, framework, deployment, verified documentation
- Linear: work items, risk, approvals, acceptance criteria
- Gmail: task handoff, completion reports, runtime evidence

## Safety boundaries

Operations such as restarting services, terminating processes, changing production databases, disabling scheduled tasks, enabling automatic recovery, rewriting Git history, and sending QQ messages require explicit user approval.

## Current architecture principle

Local runtime data remains on the Windows host. Git contains only safe source, templates, deployment automation, and redacted documentation.
