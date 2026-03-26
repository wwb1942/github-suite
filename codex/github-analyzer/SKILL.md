---
name: github-analyzer-codex
description: Codex-native repository analysis workflow for architecture reading, module mapping, and technical evaluation.
---

# github-analyzer-codex

Use this skill when the user wants to understand a repository's architecture, evaluate code quality, compare multiple repos, or prepare for modification/forking.

## Goal

Produce a technically useful repository analysis grounded in files that were actually inspected.

## Modes

- Quick overview: README, manifests, entrypoints, tests, CI
- Deep research: architecture, modules, data flow, quality signals
- Comparative: apply the same framework to multiple repositories

## Workflow

1. Confirm the target repo or local path.
2. Read top-level docs and manifests first.
3. Identify entrypoints and core modules.
4. Trace the main execution path.
5. Inspect tests, CI, and tooling.
6. Separate observed facts from inference.
7. Summarize architecture, quality, and risks.

## Evidence Rules

- Cite files for important claims.
- Label uncertain statements as inference.
- Prefer source files, tests, CI config, and manifests over secondary summaries.
- Avoid fake precision and arbitrary scoring unless the user explicitly wants a scorecard.

## Analysis Dimensions

- project structure
- architecture and boundaries
- module responsibilities
- execution and data flow
- quality signals
- reusable patterns and unusual choices

## Output Format

Structure the report like this:

- Overview
- Architecture
- Important Modules
- Quality Signals
- Risks and Gaps
- What Is Reusable
- Open Questions

## Comparative Mode

When comparing repositories:

- use the same evaluation dimensions for each repo
- normalize conclusions across repos
- end with a clear recommendation and rationale
