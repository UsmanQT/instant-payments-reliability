# Theme 4: Chaos Engineering with Money Invariants

**Status:** Not started · Milestones: Faults and money invariants, Multi-rail chaos

## Research question

Does a payment system stay financially correct during and after infrastructure failures? Can that be checked automatically with money invariants instead of only by looking at availability and latency?

## Candidate invariants

These are draft statements. Each one gets a precise definition in `docs/FINANCIAL_INVARIANTS.md` once it is implemented.

1. **Conservation:** total money across all accounts is unchanged except by recorded external inflows and outflows.
2. **No duplicate debit:** each payment intent debits the customer at most once (net of reversals).
3. **No lost payment:** every payment that settled on a rail is eventually recorded as completed by both sender and receiver.
4. **Balanced ledger:** every ledger transaction's debits equal its credits.
5. **Legal transitions:** every observed sequence of payment states is allowed by the state machine.
6. **Bounded uncertainty:** no payment stays in `UNKNOWN` longer than the reconciliation deadline.

## Method

1. Record a history of every operation during an experiment: requests, responses, rail messages and ledger writes.
2. Inject faults such as process crashes, network latency, dropped or duplicated messages, and database pauses.
3. After the faults stop and the system settles, check the invariants against the recorded history and the final database state.
4. Report violations with payment IDs and timestamps, plus metrics: time to consistency, share of payments that were ever unknown, and retry amplification.

## Prior work

This builds on the approach of Jepsen's bank test and the Elle checker (record a history, then check it), and on chaos engineering as described by Basiri et al. See [reading notes](../reading-notes).

## Findings

None yet.
