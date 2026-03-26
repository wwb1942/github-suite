---
name: github-finder
description: Codex-native GitHub project discovery workflow for technical evaluation, repository finding, and shortlisting.
---

# github-finder

Use this skill when the user wants to discover GitHub repositories for a technical requirement, compare open-source options, or shortlist candidate projects before deeper code analysis.

## Goal

Turn a vague requirement into a defensible shortlist of repositories using bounded search and primary-source validation.

## Use This Skill For

- finding open-source alternatives
- GitHub project discovery
- technical option scouting
- repo shortlisting before deeper review

## Workflow

1. Normalize the request.
   Extract product names, aliases, abbreviations, and CN/EN synonyms.
2. Build 3 to 5 search angles.
   Always include at least 3 of: direct tool, ecosystem plugin, infra/gateway, community recommendations, alternatives.
3. Search with a hard budget.
   Stop once you have 5 to 8 plausible candidates or 3 strong ones.
4. Validate top candidates from primary sources.
   Read the GitHub README, repo metadata, and recent activity.
5. Rank and report.

## Search Rules

- Prefer primary sources first: GitHub repo pages, README, docs, releases.
- Use community sources only as leads, not as the final evidence.
- Do not over-index on stars. Maintenance and fit matter more.
- Mark stale or weakly maintained projects clearly.
- If the user is Chinese-speaking, search both Chinese and English terms when useful.

## Stop Conditions

Stop searching when one of these is true:

- 3 strong candidates clearly satisfy the request
- 5 to 8 validated candidates have been collected
- new search results are mostly duplicates or weak fits

## Output Format

Return a shortlist with, for each candidate:

- name
- repo URL
- what it is
- why it matches
- risks or tradeoffs
- maintenance signal

Then end with a recommendation order.

## Optional Handoff

If the user wants deeper analysis of one repo, continue with `github-analyzer`.
