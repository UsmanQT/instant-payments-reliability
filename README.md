# Instant Payments Reliability

A research and engineering project on the **reliability and correctness of cloud-hosted instant payment systems** during distributed-systems failures.

Instant payments are fast, and in most schemes they cannot be reversed. In the cloud, timeouts, crashes, partitions and retries are routine. When a payment request times out, the sender often cannot tell whether the money moved. Retrying risks paying twice, and not retrying risks never paying. This project studies that problem from four connected angles and builds a lab to test it.

> **Status:** Phase 1 (Foundation). Nothing below is a result yet unless it is marked **Verified** and links to a reproducible experiment.

## Research themes

| # | Theme | Question | Folder |
|---|---|---|---|
| 1 | **Why payment systems fail in the cloud** | What failure patterns recur in public outage postmortems of payment and cloud infrastructure? | [`research/01-outage-postmortems`](research/01-outage-postmortems) |
| 2 | **A failure model for instant payments** | How should a system behave when a payment's outcome is unknown, retries are possible, and settlement is irrevocable? | [`research/02-failure-model`](research/02-failure-model) |
| 3 | **Exactly-once across multiple rails** | Can multi-rail instant payments achieve effectively-once processing under fault injection, using ISO 20022 message flows? | [`research/03-exactly-once-iso20022`](research/03-exactly-once-iso20022) |
| 4 | **Chaos engineering with money invariants** | Does a payment system stay financially correct (no duplicate debits, no lost credits, balanced ledgers) during infrastructure failures? | [`research/04-money-invariants`](research/04-money-invariants) |

The themes feed into each other. Failure classes from Theme 1 become the failure model in Theme 2. That model drives the rail scenarios in Theme 3, and Theme 4 checks all of it under chaos experiments.

## Repository layout

```
research/          one folder per theme: question, hypotheses, method, findings
  reading-notes/   papers, articles and standards, with citations
datasets/
  postmortems/     structured records of public incidents (Theme 1)
lab/
  baseline/        rocket-rides-atomic by Brandur Leach (MIT), imported as a reference system
  payments-lab/    this project's own instant-payments system (in development)
experiments/       experiment definitions, run scripts and reports
docs/              architecture, design documents, development log, decision records (adr/)
```

## What is inherited and what is original

| Part | Origin |
|---|---|
| `lab/baseline/` | **Inherited.** A snapshot of [brandur/rocket-rides-atomic](https://github.com/brandur/rocket-rides-atomic) at commit `94b370d`, MIT licensed. Kept as a reference implementation of Stripe-style idempotency keys to study and test against. Changes from upstream are listed in [`lab/baseline/UPSTREAM.md`](lab/baseline/UPSTREAM.md). |
| Everything else | **Original work in this project**, Apache-2.0. |

See [ADR 0002](docs/adr/0002-baseline-as-reference-system.md) for why the baseline is kept separate from the main lab.

## How work is tracked

- **[Issues](https://github.com/UsmanQT/instant-payments-reliability/issues)** hold research questions, experiments, engineering tasks and ideas, each with its own template.
- **[Milestones](https://github.com/UsmanQT/instant-payments-reliability/milestones)** correspond to the phases in [ROADMAP.md](ROADMAP.md).
- **Labels:** `theme:*` says which theme an item belongs to and `type:*` says what kind of work it is.
- **[Discussions](https://github.com/UsmanQT/instant-payments-reliability/discussions)** are for early ideas before they become issues.
- **[docs/DEVELOPMENT_LOG.md](docs/DEVELOPMENT_LOG.md)** is a dated record of what was tried, what failed and what was decided.

## How claims are labeled

Every document separates **Inherited**, **Added in this project**, **Hypothesis**, **Experiment**, **Verified result** and **Limitations**. A claim is a verified result only if it links to an experiment that anyone can rerun from this repository.

## License

Original work is licensed under [Apache-2.0](LICENSE). Third-party code keeps its own license; see [NOTICE](NOTICE).
