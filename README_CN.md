![Compatibility](https://img.shields.io/badge/Compatibility-Claude%20Code%20%2B%20Codex-4c8bf5)
![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)

# github-suite

> 同时兼容 Claude Code 与 Codex 的 GitHub 项目发现与仓库分析技能套件。

[English](README.md)

## Fork 说明

本仓库 fork 自 [`HeroAshacker/github-suite`](https://github.com/HeroAshacker/github-suite)。

- 上游项目定位：面向 Claude Code 的 GitHub 项目发现与分析技能套件
- 上游许可证：MIT
- 本 fork 保留上游归属说明，并沿用原许可证
- 本 fork 属于兼容性适配与扩展版本，不代表上游官方发布

详细归属和改动说明见 [NOTICE](NOTICE)。

## 版本区分

| 运行时 | 技能 | 用途 |
|---|---|---|
| Claude | `github-finder` | 从模糊需求中发现候选 GitHub 项目 |
| Claude | `github-analyzer` | 深度分析源码结构、架构与质量 |
| Codex | `github-finder-codex` | 带预算约束的项目发现与主源验证 |
| Codex | `github-analyzer-codex` | 基于文件证据的仓库分析与对比 |

共享方法论文档：

- [Finder Framework](shared/finder-framework.md)
- [Analyzer Framework](shared/analyzer-framework.md)
- [Runtime Differences](shared/runtime-differences.md)

## 安装方式

### Claude Code

使用 `claude/` 下的兼容版本：

```bash
git clone https://github.com/wwb1942/github-suite.git \
  ~/.claude/skill-repository/github-suite

ln -s ~/.claude/skill-repository/github-suite/claude/github-finder \
  ~/.claude/skills/github-finder
ln -s ~/.claude/skill-repository/github-suite/claude/github-analyzer \
  ~/.claude/skills/github-analyzer
```

如果你还依赖旧路径，顶层原始目录依然保留。

### Codex

将 `codex/` 下的版本链接到 Codex skills 目录：

```bash
git clone https://github.com/wwb1942/github-suite.git \
  ~/.codex/skill-repository/github-suite

ln -s ~/.codex/skill-repository/github-suite/codex/github-finder \
  ~/.codex/skills/github-finder-codex
ln -s ~/.codex/skill-repository/github-suite/codex/github-analyzer \
  ~/.codex/skills/github-analyzer-codex
```

## 使用建议

当任务是“找项目/技术选型”时，先使用 `github-finder` 或 `github-finder-codex`。

当已经有目标仓库，想理解架构、模块、质量和可复用模式时，再使用 `github-analyzer` 或 `github-analyzer-codex`。

## 许可证

[MIT](LICENSE)
