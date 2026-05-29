---
name: georiddle-maker
description: Generate, verify, and polish rigorous Chinese geography riddles for WeChat groups. Use when the user asks to create a geography riddle, hard geography puzzle, province/city/river/mountain/country guessing question, GeoRiddle, stealth geography clues, or asks to automatically verify clues, answer uniqueness, evidence, explanations, sources, confidence, and review status.
---

# GeoRiddle Maker

## Goal

Create rigorous geography riddles that are fun to guess and defensible after verification. Favor hard, indirect, evidence-backed clues over obvious tourism, culture, or landmark name-dropping. By default, make clues "stealthy": they should describe abstract geographic properties that filter candidates, not expose concrete place names that make the answer easy to locate on a map.

## Default Workflow

1. Clarify only if the request lacks a target scope. Otherwise assume a Chinese provincial-level geography riddle.
2. Generate 1 candidate answer silently unless the user specifies the answer.
3. Draft 4 clues by default; use 3 for easy, 5 for hard.
4. Draft clues as abstract filters first, then verify them. Avoid naming rivers, mountains, lakes, cities, counties, neighbors, scenic areas, or historical regimes in the riddle unless the user asks for an easier style.
5. Make each clue a verifiable proposition, not a poetic hint.
6. Search the web for evidence for every clue. Use authoritative sources when possible.
7. Require at least 2 evidence items for any clue considered strong.
8. Run a uniqueness audit: list plausible competing answers and show why the clue set excludes them. If uniqueness is not defensible, revise or add a clue.
9. Mark every clue with `verified`, `needs_review`, or `rejected`.
10. If a clue cannot be verified, revise or replace it instead of forcing it.
11. Output a final WeChat-ready riddle first, then answer, clue matching, uniqueness audit, and evidence appendix.

## Riddle Quality Rules

Prefer clues involving:

- Administrative geometry: enclaves, separated outlines, boundary anomalies, neighbor counts.
- Historical administrative geography: first-level seats, capital changes, jurisdiction chronology.
- Natural geography with precise scope: national weather stations, regional climate extrema, named basins, lake classification, elevation records.
- Textbook geography used indirectly: freshwater bodies, climate zones, terrain transitions.
- Anonymous superlatives or category membership: "the highest national station in its macro-region", "more than two textbook-required freshwater bodies", "multiple closed outline components at usable map scale", as long as the scope, date, and source are explicit in the explanation.
- Negative/absence facts: no coastline, no international border, no first-level seat for a stated historical interval, no outflow to sea, no county-level adjacency of a specified type.

Avoid clues involving:

- Direct landmark lists: famous mountains, rivers, lakes, cities, foods, celebrities.
- Clues that reveal the answer through one iconic label.
- Named neighbor chains, named basins, named mountain ranges, named rivers, named ports, named airports, and named ancient states in the riddle text when the user wants a hard puzzle.
- Claims that depend on vague wording such as "famous", "important", or "many" unless quantified.
- Historical claims without dates or administrative-level definitions.
- Clues that can be solved by typing one unique proper noun from the prompt into a map or search engine.

## Stealth Clue Style

Use this style unless the user asks for easier, educational, or beginner-friendly clues.

- Write the public riddle as property statements, not a place-name trail.
- Keep concrete names, source titles, dates, definitions, and raw facts in the answer explanation and evidence appendix.
- Prefer "the answer has property X" over "the answer contains named feature Y".
- Combine clues from different dimensions: shape/topology, climate or hydrology, textbook geography, and historical administrative chronology.
- Make no single clue enough to reveal the answer unless it is deliberately obscure and still requires cross-checking.
- If a necessary clue contains a proper noun, anonymize it in the riddle ("a national-level station in its administrative macro-region") and reveal the name only in the explanation.

## Uniqueness Audit

Before finalizing, test whether the clue set identifies one answer in the requested answer domain.

- Define the domain: e.g. 34 provincial-level regions, prefecture-level cities, county-level divisions, named rivers, mountain ranges, lakes, or countries.
- Search for likely competitors using the strongest clue keywords and broader category keywords.
- Explicitly compare at least 3 plausible competitors when the domain is large or the answer is not trivially unique.
- Mark uniqueness as `confirmed`, `probable`, or `not_established`.
- Use `confirmed` only when sources and candidate exclusion support a single answer under the stated domain and definitions.
- If uniqueness is only `probable`, say why and either add a discriminating clue or disclose the residual risk.

## Verification Standard

For each clue, record:

- `clue`: final clue text.
- `explanation`: why it points to the answer.
- `evidence`: source title, URL, date accessed, and short note.
- `confidence`: `high`, `medium`, or `low`.
- `status`: `verified`, `needs_review`, or `rejected`.

Use `verified` only when the sources directly support the wording. Use `needs_review` if evidence is partial, the wording is broad, or definitions vary. Use `rejected` if the claim is likely false or cannot be supported.

When browsing, prefer official or primary sources: government pages, statistics yearbooks, meteorological services, mapping authorities, local gazetteers, academic papers, textbook/course-standard sources, or reputable encyclopedic sources only as secondary support.

## Final Output Format

Return in Chinese:

1. WeChat riddle prompt: only the puzzle prompt and clues, no answer.
2. Answer: the answer.
3. Clue matching: numbered clue explanations.
4. Uniqueness audit: domain, candidate exclusions, and uniqueness status.
5. Evidence and review: each clue with evidence links, confidence, and status.
6. Copy-ready version: compact text suitable for WeChat.

If the user wants a file, write Markdown into the active project `outputs/` directory when available.

## Reference Pattern

Use the user's original Anhui-style example as the benchmark when available in conversation history:

- The clue hides a precise fact behind indirect wording.
- The answer is not obvious from any single clue.
- The explanation and evidence make the clue auditable.
- The best clues are verifiable claims about administrative geometry, regional statistical extremes, textbook geography, or historical administrative chronology.

Do not imitate the exact answer or claims unless requested; imitate the rigor and indirectness.

## Optional Reference

For extra checklist detail, read `references/standards.md`.
