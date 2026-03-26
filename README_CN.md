![Built with Claude Code](https://img.shields.io/badge/Built%20with-Claude%20Code-blueviolet)
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

## 本次改造

这个 fork 保留了原项目的 Claude 风格技能内容，并新增了 Codex 原生版本。

现在仓库分为三层：

- `shared/`：运行时无关的方法论
- `claude/`：Claude Code 兼容版本
- `codex/`：Codex 兼容版本

为了兼容旧用法，原来的顶层 `github-finder/` 和 `github-analyzer/` 目录仍然保留，作为 Claude 风格的旧入口。

## 技能列表

| 运行时 | 技能 | 用途 |
|---|---|---|
| Claude | `github-finder` | 从模糊需求中发现候选 GitHub 项目 |
| Claude | `github-analyzer` | 深度分析源码结构、架构与质量 |
| Codex | `github-finder-codex` | 带预算约束的项目发现与主源验证 |
| Codex | `github-analyzer-codex` | 基于文件证据的仓库分析与对比 |

## 共享方法论

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

## 运行时策略

### Claude Code 版本

- 保留原始的工作流导向风格
- 保留 Claude 风格的工具命名和链式调用假设
- 适合 Claude Code 的 SKILL 工作流

### Codex 版本

- 使用 Codex 原生表达方式
- 避免 Claude 专属工具名和调用语法
- 更强调 shell-first、主源验证、搜索预算控制

## 使用建议

当任务是“找项目/技术选型”时，先使用 `github-finder` 或 `github-finder-codex`。

当已经有目标仓库，想理解架构、模块、质量和可复用模式时，再使用 `github-analyzer` 或 `github-analyzer-codex`。

## 状态

| 层 | 状态 |
|---|---|
| 共享方法论 | 可用 |
| Claude 兼容层 | 可用 |
| Codex 兼容层 | 可用 |

## 许可证

[MIT](LICENSE)

## 归属说明

- 原始上游仓库：[`HeroAshacker/github-suite`](https://github.com/HeroAshacker/github-suite)
- 本 fork 主要新增：
  - 双运行时仓库结构
  - Codex 原生 SKILL 版本
  - 共享方法论文档
  - 双平台安装说明
- 本 fork 不声称获得上游作者背书，也不将本 fork 改动表述为上游官方版本。
