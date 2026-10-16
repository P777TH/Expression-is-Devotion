---
title: Related Projects
description: Relationship between Expression is Devotion, Superteam, and the discipleship framework
---

## Included Repositories

| Repository | Workspace location | Purpose | Status |
| --- | --- | --- | --- |
| [Racecar Discipleship Framework](https://github.com/trust-fullstop/racecar-discipleship-framework) | [`projects/racecar-discipleship-framework/`](../../projects/racecar-discipleship-framework/) | Twelve character studies and proposed AI-agent persona framework | Added as submodule at `47140f3668c97ef96eabdb759fae05fd25ade71b` |
| [Superteam](https://github.com/trust-fullstop/superteam) | `projects/superteam/` (pending access) | Intended build-time squad for this project | GitHub API returned 404 and Git fetch returned 403 from this environment |

## How They Relate

The discipleship framework README calls itself exploration-only, says it is
not wired into a live agent session, and says it is not a replacement for
Superteam. Its [roster](../../projects/racecar-discipleship-framework/ROSTER.md)
does map disciple personas to Superteam roles. Use that material as guidance
for team formation and collaboration, not as executable agent configuration.

Superteam is intended to help build the Expression is Devotion application.
That makes it development tooling, not a runtime dependency of the fundraising
platform. Keep the repositories independently versioned and do not merge
personas, product roles, account permissions, or financial authority.

## Access Status

The discipleship repository is included at
[`projects/racecar-discipleship-framework/`](../../projects/racecar-discipleship-framework/)
as a submodule. Initialize it in a fresh clone with:

```bash
git submodule update --init --recursive
```

This Codespace cannot read Superteam yet: GitHub returned `404 Not Found` from
the API and `403` for `git ls-remote`. Once this environment's Git credential
or GitHub App has read access, add it as a second submodule at
`projects/superteam/` and inspect its actual agent/configuration files before
activating anything. Do not paste credentials into chat.