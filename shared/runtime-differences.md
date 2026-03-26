# Runtime Differences

This repository supports two agent runtimes with different conventions.

## Claude Code

- Claude-style SKILL frontmatter and tool naming
- Can rely on Claude Code skill chaining conventions
- Keep the original skill behavior intact for compatibility

## Codex

- Codex-native SKILL wording and workflow
- Do not assume Claude-only tool names or orchestration syntax
- Prefer concrete shell-first workflows and explicit file references
- When browsing is needed, prefer primary sources and bounded search loops

## Authoring Rule

Shared methodology belongs in `shared/`.
Runtime-specific execution instructions belong in `claude/` or `codex/`.
