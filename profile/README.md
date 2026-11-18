<p align="center">
  <a href="https://www.npmjs.com/package/@appitlabs/skills"><img alt="npm" src="https://img.shields.io/npm/v/@appitlabs/skills?style=flat-square&color=CB3837"></a>
  <a href="https://www.npmjs.com/package/@appitlabs/skills"><img alt="downloads" src="https://img.shields.io/npm/dm/@appitlabs/skills?style=flat-square"></a>
  <a href="https://github.com/Appit-labs/appit-skills"><img alt="skills" src="https://img.shields.io/badge/skills-12-2EA043?style=flat-square"></a>
  <img alt="agents" src="https://img.shields.io/badge/works%20in-pi%20%7C%20Claude%20Code%20%7C%20Codex%20%7C%20Cursor-4B5563?style=flat-square">
  <a href="https://github.com/Appit-labs/appit-skills/blob/main/LICENSE"><img alt="license" src="https://img.shields.io/badge/license-MIT-3DA639?style=flat-square"></a>
</p>

<h3 align="center">We build AI products, and the tools that keep them shipping.</h3>

<p align="center">
  <a href="https://github.com/Appit-labs/appit-skills"><img alt="skills" src="https://img.shields.io/badge/agent%20skills-9%20of%20them-2EA043?style=flat-square"></a>
  <img alt="agents" src="https://img.shields.io/badge/works%20in-pi%20%7C%20Claude%20Code%20%7C%20Codex%20%7C%20Cursor-4B5563?style=flat-square">
  <a href="https://github.com/Appit-labs/appit-skills/blob/main/LICENSE"><img alt="license" src="https://img.shields.io/badge/license-MIT-3DA639?style=flat-square"></a>
</p>

## What lives here

**Appit** is where our AI and application projects live. Repositories here fall into three groups:

| Group | What it is |
| --- | --- |
| **Agent skills** | Practical, MIT-licensed skills that make coding agents better at real work — browser QA, CI triage, databases, remote servers, Blender. Start at [appit-skills](https://github.com/Appit-labs/appit-skills). |
| **Apps** | The product code itself: services, daemons, UIs. |
| **Tooling** | The small utilities that keep the two above honest — probes, harnesses, demos. |

## The skills collection

Twelve skills, one install, any agent. Each one is plain `SKILL.md` plus, where it helps, a single
stdlib script — no runtime, no framework, nothing tied to one vendor.

```bash
# npm — all twelve in one package
npm i -g @appitlabs/skills        # or: pi install npm:@appitlabs/skills

# Claude Code
claude plugin marketplace add Appit-labs/appit-skills
claude plugin install live-qa@appit-skills

# pi
pi install git:github.com/Appit-labs/appit-skills

# anything else that reads a skills directory
git clone git@github.com:Appit-labs/live-qa.git && cp -r live-qa/skills/live-qa ~/.codex/skills/
```

| Skill | What it does |
| --- | --- |
| [live-qa](https://github.com/Appit-labs/live-qa) | Live QA in a real browser: a verified screenshot per step, a pass/fail table, console/network facts |
| [ci-triage](https://github.com/Appit-labs/ci-triage) | CI is red → the failing step and the four lines that matter (GitHub Actions + GitLab) |
| [pg-inspect](https://github.com/Appit-labs/pg-inspect) | Read-only Postgres inspection that cannot write |
| [repo-runbook](https://github.com/Appit-labs/repo-runbook) | Writes the install/test/migrate runbook into `AGENTS.md` |
| [remote-exec](https://github.com/Appit-labs/remote-exec) | SSH that cannot hang; one-call host health probe |
| [trello-tickets](https://github.com/Appit-labs/trello-tickets) | Seven ticket types baked in; well-formed cards in one command |
| [cloud-browser](https://github.com/Appit-labs/cloud-browser) | Hosted browser sessions, and the sweep that stops orphaned ones |
| [open-design](https://github.com/Appit-labs/open-design) | The OpenDesign monorepo, minus the pnpm trap |
| [blender-pipeline](https://github.com/Appit-labs/blender-pipeline) | Blender via MCP: eight playbooks behind one router |

## How we build them

- **Measured first.** Every skill started as a number in our own session logs — 16,315 grep crawls,
  1,115 retyped `psql` commands, 825 hand-written `ssh` calls.
- **Token-frugal.** Descriptions are short because every description is paid on every session;
  detail lives in `references/` and is read only when it is needed.
- **Scanned.** Each skill ships a SkillSpector baseline and a `SECURITY.md` that lists every accepted
  finding and why. No `shell=True`, no bundled credentials, no runtime-chosen destinations.
- **Verified.** Scripts carry `--self-test`, and every command in the docs was run against a real
  target before it was written down.

## Working with us

Issues and pull requests are welcome in the skill repositories. For anything security-sensitive,
email first rather than opening a public issue.
