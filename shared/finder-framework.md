# Finder Framework

This document captures the reusable method behind the project-discovery skill.
It is runtime-neutral and can be shared by Claude Code and Codex variants.

## Goal

Turn an ambiguous user requirement into a short, defensible list of GitHub repositories worth deeper evaluation.

## Core Principles

- Resolve terminology first. Product codenames, abbreviations, and mixed CN/EN terms should be normalized before searching.
- Search from multiple angles. Do not rely on one literal GitHub query.
- Prefer evidence over popularity. Stars matter, but README clarity, maintenance recency, and fit matter more.
- Stop early once confidence is high enough. Search budget should be finite.

## Recommended Search Loop

1. Clarify the requirement.
2. Expand terms and synonyms.
3. Search across at least 3 angles.
4. Read README pages for the strongest candidates.
5. Expand via README references, topics, and community mentions only if needed.
6. Rank the best 5 to 8 options.

## Search Angles

- Direct tool or library
- Plugin or extension in an existing ecosystem
- Gateway, proxy, or infrastructure layer
- Community recommendation lists
- Alternatives to a known project

## Evaluation Dimensions

- Functional fit
- Maintenance recency
- Documentation quality
- Community health
- Architecture clarity
- Integration cost

## Stop Conditions

Stop when any of these become true:

- 3 strong candidates clearly satisfy the request
- 5 to 8 candidates have been validated from primary sources
- Additional searching only produces duplicates or weak matches

## Output Shape

Use a compact comparison with:

- project name
- repo URL
- why it matches
- main risks or tradeoffs
- recommendation rank
