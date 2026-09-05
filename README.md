# dotagents

Shared agent skill pack for [dotagents](https://dotagents.sentry.dev/).

Each skill is a top-level directory with a `SKILL.md` so `@sentry/dotagents` can discover it. Private skills do not belong here — keep those on a local `path:` or in a private repo.

## Install

Add every skill from this repo:

```bash
npx @sentry/dotagents add miltonparedes/dotagents --all
```

Or add named skills:

```bash
npx @sentry/dotagents add miltonparedes/dotagents python-standards review-triage pr-title
```

Then install declared dependencies:

```bash
npx @sentry/dotagents install
```

See `agents.toml.example` for a full declaration you can copy into your own `agents.toml`.

## Skills

| Skill | Description |
| --- | --- |
| [codex](codex/SKILL.md) | Run Codex for analysis, review, and second opinions |
| [cross-service-research](cross-service-research/SKILL.md) | Research and plan across multiple repos; write findings to Obsidian |
| [pr-title](pr-title/SKILL.md) | Set PR/MR titles as semantic commits for squash-merge workflows |
| [python-standards](python-standards/SKILL.md) | Python project standards (`uv`, FastAPI, typing, linting, testing) |
| [review-triage](review-triage/SKILL.md) | Fetch and triage GitHub/GitLab review comments |
| [skill-exporter](skill-exporter/SKILL.md) | Export a local Claude skill into a versioned git repo |
| [ts-bun-review](ts-bun-review/SKILL.md) | Review TypeScript for correct Bun API usage |
| [ts-deno-review](ts-deno-review/SKILL.md) | Review TypeScript for correct Deno API usage |

`python-standards` includes nested skills and references: `code-quality`, `io-patterns`, `project-setup`, `testing`, and `references/`.

## Private skills

This repo is public. Anything you do not want shared stays out of it.

Use a local path:

```toml
[[skills]]
name = "private-skill"
source = "path:./private/my-skill"
```

Or point at a private GitHub repo you trust:

```toml
[[skills]]
name = "private-skill"
source = "you/private-dotagents"
```

## Layout

```
codex/
cross-service-research/
pr-title/
python-standards/
review-triage/
skill-exporter/
ts-bun-review/
ts-deno-review/
```
