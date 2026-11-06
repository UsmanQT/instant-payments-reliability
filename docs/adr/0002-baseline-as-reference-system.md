# ADR 0002: Keep rocket-rides-atomic as a separate reference system

**Date:** 2026-11-05 · **Status:** Accepted

## Context

No maintained open-source project covers this project's research themes together. The strongest existing project on the core problem (Theme 2) is [brandur/rocket-rides-atomic](https://github.com/brandur/rocket-rides-atomic) (MIT). It implements Stripe-style idempotency keys, atomic phases, recovery points, a completer, a staged job queue and a key reaper around an irreversible charge. But it is a ride-sharing demo: it has no ledger, no payment rails and no ISO 20022.

The options considered were:

1. Fork it and grow it into the whole lab.
2. Import it unchanged as a reference system, and build the lab separately.
3. Cite it only.

## Decision

Option 2. Import a snapshot into `lab/baseline/`, change it only as needed to run and test it, and record every change in `lab/baseline/UPSTREAM.md`. Build the instant-payments system separately in `lab/payments-lab/`.

## Reasons

- Inherited code and original work are separated by a folder boundary, not mixed in one codebase.
- Early experiments test an independent, well-known design rather than this project's own code.
- Later experiments can run the same fault scenarios against both systems for a direct comparison.
- payments-lab can be designed for instant payments from the start instead of being adapted from a rides app.

## Consequences

- The baseline is imported as a file snapshot without upstream git history, so this repository's history starts with this project. Provenance (upstream URL and commit) is recorded in `NOTICE` and `UPSTREAM.md`.
- The baseline stays in Ruby while payments-lab uses Python (ADR 0003).
