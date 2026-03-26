![Compatibility](https://img.shields.io/badge/Compatibility-Claude%20Code%20%2B%20Codex-4c8bf5)
![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)

# github-suite

> Dual-runtime GitHub discovery and repository analysis skill suite for Claude Code and Codex.

[中文文档](README_CN.md)

## Fork Notice

This repository is a fork of [`HeroAshacker/github-suite`](https://github.com/HeroAshacker/github-suite).

- Upstream project: GitHub discovery and analysis SKILL suite for Claude Code
- Upstream license: MIT
- This fork keeps attribution to the upstream project and preserves the original license
- This fork is an adaptation layer, not an official upstream release

See [NOTICE](NOTICE) for attribution and modification details.

## Variants

| Runtime | Skill | Purpose |
|---|---|---|
| Claude | `github-finder` | Discover repositories from ambiguous user requirements |
| Claude | `github-analyzer` | Deep repository analysis and comparison |
| Codex | `github-finder-codex` | Bounded GitHub discovery with primary-source validation |
| Codex | `github-analyzer-codex` | File-grounded architecture and quality analysis |

Shared documents:

- [Finder Framework](shared/finder-framework.md)
- [Analyzer Framework](shared/analyzer-framework.md)
- [Runtime Differences](shared/runtime-differences.md)

## Installation

### Claude Code

Use the Claude-compatible copies under `claude/`.

```bash
git clone https://github.com/wwb1942/github-suite.git \
  ~/.claude/skill-repository/github-suite

ln -s ~/.claude/skill-repository/github-suite/claude/github-finder \
  ~/.claude/skills/github-finder
ln -s ~/.claude/skill-repository/github-suite/claude/github-analyzer \
  ~/.claude/skills/github-analyzer
```

If you rely on the old layout, the original top-level folders are still available.

### Codex

Copy or symlink the Codex-native folders into your Codex skills directory.

```bash
git clone https://github.com/wwb1942/github-suite.git \
  ~/.codex/skill-repository/github-suite

ln -s ~/.codex/skill-repository/github-suite/codex/github-finder \
  ~/.codex/skills/github-finder-codex
ln -s ~/.codex/skill-repository/github-suite/codex/github-analyzer \
  ~/.codex/skills/github-analyzer-codex
```

## Usage

Use `github-finder` or `github-finder-codex` first when the task is repository discovery.

Use `github-analyzer` or `github-analyzer-codex` after you already have a target repository and want to understand its architecture, module layout, and quality signals.

## License

[MIT](LICENSE)
