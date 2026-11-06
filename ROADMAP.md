# Roadmap

Each phase is a GitHub milestone and ends with a tagged release. Phases 2 and 3 run in parallel: one is code, the other is reading and data collection.

| Phase | Milestone | Themes | Outcome | Tag |
|---|---|---|---|---|
| 1 | **Foundation** | — | Baseline runs locally and in CI; its architecture is documented; project tracking is in place | `v0.1` |
| 2 | **Baseline failure study** | 2 | First experiments against the baseline (crashes between recovery points, key reaping during an unknown outcome); `FAILURE_MODEL.md` v0 | `v0.2` |
| 3 | **Postmortem dataset v1** | 1 | Record schema, about 30 public incidents coded, first taxonomy, each failure class mapped to a lab scenario | `v0.3` |
| 4 | **payments-lab core** | 2 | Own system in Python: double-entry ledger, payment state machine with `UNKNOWN`, durable idempotency, outbox, reconciliation | `v0.4` |
| 5 | **Rails and ISO 20022** | 3 | `Rail` interface; instant-rail simulator (pacs.008 in, pacs.002 out, pacs.028 status inquiry); irrevocable settlement; timeout after settlement | `v0.5` |
| 6 | **Faults and money invariants** | 4 | Fault scenarios, invariant checker, per-run reports; first measured comparison of baseline and payments-lab | `v0.6` |
| 7 | **Multi-rail chaos and publication** | 3, 4 | Second rail, failover during unknown outcomes, repeated trials, published write-ups | `v1.0` |

## Later ideas (not scheduled)

- Run the same fault scenarios and invariants against independent open-source payment systems, such as [Mojaloop](https://github.com/mojaloop) and [Bank of Anthos](https://github.com/GoogleCloudPlatform/bank-of-anthos).
- Deploy the lab on AWS (EKS or ECS) with infrastructure as code, and compare failure behavior on managed infrastructure.
- Extract the invariant checker or the postmortem dataset into a separate repository if others start using it.

## How to update this file

When a phase finishes, add the date and a link to its release. Do not delete phases; mark them done.
