# Theme 3: Exactly-Once Guarantees in Multi-Rail Instant Payments

**Status:** Not started · Milestones: Rails and ISO 20022, Multi-rail chaos

## Research question

Can a payment system that sends payments over more than one instant rail achieve effectively-once processing (each payment settles exactly once) when messages are delayed, lost or duplicated, and when rails time out?

## Background

Networks deliver messages at least once or at most once; "exactly once" is achieved, if at all, by combining retries with deduplication at each step. ISO 20022 gives each payment identifiers (such as the end-to-end ID and UETR) and status messages (such as pacs.002 status reports and pacs.028 status requests) that can support this. Whether they are enough under faults is the question.

## Sub-questions

1. Which ISO 20022 identifiers and messages are needed to deduplicate and to resolve unknown outcomes on one rail?
2. When a payment's outcome on rail A is unknown, is it ever safe to fail over to rail B? What must be true first?
3. How do acknowledgment, rejection and timeout semantics differ between rails, and how do those differences affect correctness?

## Working hypotheses

- **H3.1:** Failing over to a second rail while the first rail's outcome is unknown can cause double payment unless the first payment is first confirmed rejected or recalled.
- **H3.2:** A status-inquiry (pacs.028) step resolves most unknown outcomes. The cases it cannot resolve are still to be identified.

## Scope and limits

The rails in this project are **simulators informed by published message schemas**. They do not claim to conform to the operating rules of FedNow, RTP, TIPS or any other real scheme.

## Findings

None yet.
