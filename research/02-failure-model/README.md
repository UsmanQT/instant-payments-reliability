# Theme 2: A Failure Model for Cloud-Hosted Instant Payments

**Status:** Starting with the baseline study · Milestones: Baseline failure study, payments-lab core

## Research question

When a payment request times out and its outcome is unknown, how should a system decide whether to retry, wait, inquire or reverse, given that instant settlement is usually irrevocable?

## Sub-questions

1. What states does a payment pass through, and in which of them is its outcome unknown to the sender?
2. Which failure points (crash, timeout, lost or late response, duplicate request) lead to duplicate debits, and which lead to lost payments?
3. How long can idempotency state be kept? What happens if it expires while an outcome is still unknown?
4. What is the minimum a reconciliation process needs in order to resolve every unknown outcome?

## Working hypotheses

These are untested hypotheses, not findings.

- **H2.1:** The baseline's atomic-phase design prevents duplicate charges when a client retries with the same key after a crash at any recovery point.
- **H2.2:** If the reaper removes a key before the completer resolves its request, a later retry with the same key can create a second charge.
- **H2.3:** Without a status-inquiry step to the rail, some unknown outcomes cannot be resolved automatically.

## Method

1. Study the baseline in `lab/baseline`: document each recovery point and what survives a crash there.
2. Write experiments that inject a crash or timeout at each point, then check for duplicate or missing charges.
3. Generalize the findings into `docs/FAILURE_MODEL.md` and `docs/PAYMENT_STATE_MACHINE.md`.
4. Implement the model in `lab/payments-lab` and test it with the same experiments.

## Findings

None yet.
