# Analyzer Framework

This document captures the reusable method behind the source-analysis skill.
It is runtime-neutral and can be shared by Claude Code and Codex variants.

## Goal

Produce a technically useful understanding of a repository without pretending to have certainty where the code has not been read.

## Analysis Modes

- Quick overview: README, entrypoints, package manifest, repo layout, tests, CI
- Deep research: architecture, modules, data flow, design decisions, quality signals
- Comparative: same framework applied to multiple repositories

## Evidence Rules

- Distinguish observed facts from inference.
- Cite files for important claims.
- Prefer primary sources: README, manifests, source files, tests, CI config.
- Avoid fake numeric scoring unless the user explicitly wants it.

## Core Dimensions

- Structure and repo layout
- Architecture and boundaries
- Main modules and responsibilities
- Data flow and execution path
- Quality signals: tests, lint, CI, error handling
- Distinctive patterns or implementation choices

## Reading Order

1. README and top-level docs
2. Build/runtime manifests
3. Entry files
4. Core modules
5. Tests and CI
6. Auxiliary tooling and scripts

## Output Shape

Recommended report sections:

- Overview
- How it works
- Architecture
- Important modules
- Quality and risks
- What is reusable
- Open questions
