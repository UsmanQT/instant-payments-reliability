# Lab

| Folder | What it is | Status |
|---|---|---|
| [`baseline/`](baseline) | **Inherited.** rocket-rides-atomic by Brandur Leach (MIT), a reference implementation of Stripe-style idempotency keys around an irreversible charge. Studied and tested, not extended. See [`baseline/UPSTREAM.md`](baseline/UPSTREAM.md). | Imported; not yet running in this repository |
| [`payments-lab/`](payments-lab) | **Original.** This project's own instant-payments system, where the failure model, rails, ISO 20022 simulation and invariants are built. | Design stage |

The same experiments in [`experiments/`](../experiments) run against both, so the baseline gives every result a fixed point of comparison.
