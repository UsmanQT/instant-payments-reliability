# payments-lab

**Status:** design stage. No code yet. Work is planned under the *payments-lab core* milestone.

This is the project's own instant-payments system. It applies the idempotency and recovery-point pattern studied in `../baseline` to instant bank-to-bank payments, and extends it.

## Planned components

| Component | Purpose | Milestone |
|---|---|---|
| Ledger | Double-entry ledger with balanced transactions | payments-lab core |
| Payment state machine | Explicit states, including `UNKNOWN` for unresolved outcomes | payments-lab core |
| Idempotency store | Durable keys with request fingerprinting, stored in the database | payments-lab core |
| Outbox | Transactionally staged messages to the rail | payments-lab core |
| Reconciliation | Resolves `UNKNOWN` payments through status inquiry and rail reports | payments-lab core |
| `Rail` interface and simulators | ISO 20022 instant-rail simulators with acknowledgment, reject, timeout and irrevocable settlement | Rails and ISO 20022 |
| Fault hooks | Points where experiments can inject crashes, delays and duplicates | Faults and money invariants |

## Technology

Python and PostgreSQL, run with docker-compose. See [ADR 0003](../../docs/adr/0003-python-for-payments-lab.md).
