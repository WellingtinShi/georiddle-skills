# GeoRiddle Standards

## Strong Clue Checklist

A clue is strong when all are true:

- It is falsifiable.
- It has a clear geographic or historical scope.
- It can be checked from maps, official statistics, yearbooks, gazetteers, papers, or textbooks.
- It does not reveal the answer through a famous name alone.
- It narrows the candidate set when combined with other clues.
- It works as an abstract candidate filter in the public riddle, with concrete names saved for the explanation.
- It is hard to solve by pasting one proper noun from the riddle into a map or search engine.

## Stealth Riddle Checklist

Use this checklist for hard WeChat riddles:

- Replace named features in the riddle with typed descriptions: "a national-level weather station", "a textbook-required freshwater body", "a first-level administrative seat", "a closed outline component".
- Use at least three clue dimensions, such as boundary topology, climate or hydrology, textbook geography, and historical administrative geography.
- Keep dates, official definitions, and source names in the explanation, not the riddle, unless the date itself is the puzzle mechanism.
- Avoid named neighbor lists, named rivers, named mountains, named lakes, named scenic areas, named cities, and named ancient states in the public prompt.
- Prefer clues that are independently weak but jointly decisive.
- If a clue uses a superlative, state its comparison class in the explanation: country, macro-region, province, basin, climate zone, or administrative level.

## Uniqueness Checklist

Before final output, establish whether the answer is unique:

- State the answer domain exactly.
- Identify likely competitors from the strongest individual clues.
- Compare at least 3 competitors for broad domains such as provinces, prefecture-level cities, rivers, mountains, lakes, or countries.
- Explain which clue excludes each competitor.
- Mark `confirmed` only when the remaining candidate set is one under the stated definitions.
- Mark `probable` when sources suggest uniqueness but the available source set is incomplete or definitions vary.
- Mark `not_established` when multiple candidates remain; revise the riddle before publishing unless the user explicitly accepts ambiguity.

## Preferred Evidence Types

- Administrative boundaries: official maps, civil affairs data, gazetteers, GIS boundary datasets.
- Climate and meteorology: national meteorological data, station records, climate normals, yearbooks.
- Lakes and rivers: water-resource authorities, official lake catalogs, textbook materials, maps.
- Historical administration: historical atlases, gazetteers, academic references, official local histories.
- Human geography: census data, statistical yearbooks, transport authority pages, cultural geography references.

## Risk Flags

- The clue uses "largest", "highest", "first", "only", or "most" without a date, region, and source.
- The clue uses modern administrative borders to describe historical periods without saying so.
- The clue mixes province, city, station, scenic area, and natural feature statistics.
- The clue relies on a lake/river crossing or adjacency but does not define whether adjacency counts.
- The clue is true for many answers and does not narrow enough.
- The public riddle contains enough named geography for a solver to locate the answer directly.
- The answer is verified, but plausible alternative answers were not checked.
