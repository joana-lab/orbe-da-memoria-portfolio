# Product method

Orbe's method is a single sentence made operational: **the experience is a derivative of the
data.** Product work is therefore, first, data-model work — and only then interface work.

## The pipeline

```
Source  →  Verification  →  Structured claim  →  Experience
```

1. **Source.** A candidate claim starts from an archival or primary source, identified and, where
   possible, linked to a navigable document (not a dry catalogue record).
2. **Verification.** A human verifies the claim against the source, outside the agent that drafted
   it. The output is not "true/false" but a **grade** plus, where relevant, a **declared gap**.
3. **Structured claim.** The verified claim is written as a structured record: claim text, source,
   certainty grade, nature of source, dating, coordinates, relationships.
4. **Experience.** Maps, entity pages, and narrative panels are rendered from those records.

## Fields that drive the interface

| Field | Drives |
|---|---|
| `claim` | what the interface may state |
| `source` | the citation shown, linked to the document where possible |
| `certainty.grade` | how confidently it is stated (word + symbol) |
| `certainty.natureOfSource` | one of the two source axes |
| `certainty.dating` | the second source axis (kept separate from the first) |
| `timeAnchor` | timeline placement and "same period" queries |
| `coordinates` + `coordinateState` | map placement and whether the point is candidate or audited |
| `relationships` | the cross-collection knowledge network |

A worked, sanitised record is in
[../examples/structured-content-example.json](../examples/structured-content-example.json).

## The certainty vocabulary

Certainty is expressed as **word plus symbol**, never colour alone and never a percentage. Grades
range from documented, through attributed and tradition, to states such as *in conflict* (two
identified sources that disagree), *reconstruction*, and *candidate* (a working state, not a
publishable grade). The point is that the label tells the truth about how much is known — and
never inflates it to fit a nicer interface.

Two axes are deliberately **not fused**:

- the **grade of the claim** (how well the evidence supports it), and
- the **nature and dating of the source** (what kind of source it is, and whether it is
  contemporary or later).

Fusing them would let a comfortable, easy-to-access source masquerade as strong evidence. They
are orthogonal, and shown as such.

## Honest absence

When a source or coordinate is missing, the interface renders a **stated gap** — "we have not
located this in this dossier" — rather than a blank or a confident-looking guess. Two disciplines
protect this:

- **Absence is localised, never universal.** "Not located in this dossier" ≠ "does not exist";
  the humble version is also the more defensible one.
- **Prove the instrument before declaring the absence.** A gap declared with a broken tool is an
  error dressed as virtue.

## Why this is a product decision, not a data-entry decision

Treating provenance and certainty as product capabilities changes what "good" means. A feature is
not done when it looks finished; it is done when each claim it shows is sourced, graded, and — if
incomplete — honest about it. That standard is what makes the atlas usable as a *reference*, which
is the product's reason to exist.
