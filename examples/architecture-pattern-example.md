# Architecture pattern: the experience as a function of the data

This is an **illustrative pattern**, written for the portfolio. It is not production source code;
it shows *how* the platform derives an interface from structured records like
[structured-content-example.json](structured-content-example.json).

## Pattern 1 — render a claim from its record

A claim is never free text in the UI; it is rendered from its fields, so the certainty grade and
the source are always present and consistent.

```js
// Illustrative — not production code.
const GRADES = {
  "documented":     { word: "documented",     symbol: "●" },
  "attributed":     { word: "attributed",     symbol: "◑" },
  "tradition":      { word: "tradition",      symbol: "◇" },
  "in-conflict":    { word: "in conflict",    symbol: "⋔" },
  "reconstruction": { word: "reconstruction", symbol: "△" },
  "candidate":      { word: "candidate",      symbol: "○" } // a state, not a publishable grade
};

function renderClaim(claim, sourceById) {
  const grade = GRADES[claim.grade];
  const source = sourceById[claim.sourceRef];

  // Grade shown as WORD + SYMBOL — never colour alone, never a percentage.
  const gradeLabel = `${grade.symbol} ${grade.word}`;

  // Two independent axes, kept separate: nature of source, and dating.
  const sourceAxes = source
    ? `${claim.natureOfSource} · ${claim.dating}`
    : null;

  // A claim without a resolvable source degrades to an honest, stated gap.
  const citation = source
    ? linkToDocument(source)      // clickable only when a real document URL exists
    : "source not located in this dossier";

  return { text: claim.text, gradeLabel, sourceAxes, citation };
}
```

The important properties are structural, not cosmetic:

- **Grade is word + symbol.** Colour never carries meaning alone (accessibility and honesty).
- **Two axes never fuse.** `natureOfSource` (kind of evidence) and `dating` (contemporary vs
  later) are separate fields and separate UI elements.
- **Absence is first-class.** A missing source produces a stated gap, not a blank or a guess.

## Pattern 2 — the map reacts to intent

```js
// Illustrative — not production code.
// The map is a reactive surface, not a catalogue: it activates on a query
// that returns map actions, and stays calm at rest.
function onQuery(result) {
  if (result.mapActions?.length) {
    activateMap(result.mapActions);   // expand, fly to, draw routes
  } else {
    keepMapAtRest();                  // compact, centred, no forced content
  }
}
```

## Pattern 3 — readiness derived from data, not declared

```js
// Illustrative — not production code.
// Publication readiness is computed from the record, so "ready" is a fact, not an opinion.
function claimBlocksPublication(claim, sourceById) {
  const reasons = [];
  if (!GRADES[claim.grade]) reasons.push("unknown grade");
  if (claim.grade === "candidate") reasons.push("candidate is not a publishable grade");
  if (!sourceById[claim.sourceRef]) reasons.push("no source");
  return reasons; // empty array == publishable
}
```

These patterns are simplified for clarity. The production implementation, its data, and its
checks remain private.
