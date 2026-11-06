# ADR 0001: One repository for all four themes

**Date:** 2026-11-05 · **Status:** Accepted

## Context

The project has four research themes: outage postmortems, a failure model, exactly-once processing with ISO 20022, and chaos experiments with money invariants. They could live in separate repositories or in one.

## Decision

Keep all four themes in this repository. Each theme has its own folder under `research/` and its own `theme:*` label. All themes share the code in `lab/` and the experiment tools in `experiments/`.

## Reasons

- The themes depend on each other. Postmortem failure classes become the failure model, the model drives the rail scenarios, and the invariants check all of it.
- One issue tracker, one roadmap and one release history keep cross-references between research and code direct.

## Consequences

If a part becomes useful on its own, such as the postmortem dataset or the invariant checker, it can be extracted into its own repository later. This repository stays the umbrella and links to it.
