# Governance

Governance is the part of Orbe that does not scale automatically — by design. The product can
industrialise the *machine*; it never industrialises the *stamp*.

## The three gates

### Truth
Nothing is considered **verified** without human verification, and that verification is performed
**outside** the agent (or person) that produced the work. Plausibility is not proof. A claim that
cannot be traced to a source does not get a confident grade — it becomes a declared gap.

### Scale
Only the founder creates or expands the agent roster. Agents do not create agents. Growth of the
delivery system is a human decision, precisely because it changes how much can be produced before
a human sees it.

### Continuity
A decision is **durable** only when it is **both**:

- approved by the founder, **and**
- written into version-controlled source of truth.

An approval that lives only in a conversation is not durable — it will be forgotten or
contradicted. The cure for "we decided this and lost it" is not to decide again; it is to write
state, owner, and revision into the repository.

> **Done is not a chat message. Done is a verified state visible in version-controlled source.**

## Why the gates are shaped this way

- **A rule that only protects you from subordinates protects you from nothing.** The governance
  model must be able to stop the founder too — the person who approves is bound by the same
  requirement that a claim be sourced and a decision be written down.
- **What is entrusted to discipline alone is eventually lost.** "We'll check this by hand" is a
  good promise only until someone is tired. Where a check can be an instrument, it becomes one;
  the instrument reports, the human decides.
- **An honest absence is an assertion, and is proven as such.** Before saying "not found", prove
  the instrument that measured it was sound. A false honest-absence is worse than an error,
  because it wears the clothing of the method.

## How governance shows up in the product

- Every public claim carries a source and an explicit certainty grade.
- Certainty is expressed as **word plus symbol**, never colour alone and never a percentage.
- Two axes — the **grade of the claim** and the **nature/dating of the source** — are kept
  distinct and never fused.
- Missing data renders as a stated gap, not a blank or a guess.
- Releases are verified *served == built* and recorded, so "live" is a proven state, not a claim.

## Relationship to AI

The AI operating model ([ai-operating-model.md](ai-operating-model.md)) is the *engine*;
governance is the *set of gates the engine runs through*. Agents accelerate everything up to each
gate. The gates do not move because the engine got faster.
