# Category file schema

Every file in `categories/` has YAML front-matter and five fixed sections.
The analysis flow reads these files directly — they are the instructions.

Front-matter fields:
- `id` — kebab-case, stable forever, used in analysis JSON
- `name` — human-readable
- `added` — methodology version that introduced it

Sections (all required):
1. `## Definition` — one paragraph
2. `## Flag when` — numbered, text-checkable criteria
3. `## Do NOT flag when` — explicit exclusions (this is what keeps flags
   defensible; when in doubt, do not flag)
4. `## Examples` — at least one flagged passage with a suggested rewrite,
   and at least one passage that must NOT be flagged, with the reason
5. `## Sources` — citations grounding the category (IDs from SOURCES.md
   where available, full citations otherwise)

## "Historically established"

Several criteria use "historically established" (or refer to a figure's disputed status in the scholarly literature). Both mean: supported by a
source in SOURCES.md or by cited mainstream scholarship. When a flag's
explanation depends on such a claim, the analysis records the supporting
source as a `contextFacts` entry with its `sourceId`. If no source can be
named, the claim is not established and the flag is not made.
