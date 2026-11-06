# ADR 0003: Python for payments-lab

**Date:** 2026-11-05 · **Status:** Accepted

## Context

payments-lab needs a ledger, a state machine, HTTP services, rail simulators, and tooling for experiments and analysis. The baseline is in Ruby.

## Decision

Write payments-lab, the invariant checker and the experiment tooling in Python, with PostgreSQL, run through docker-compose.

## Reasons

- Python is the author's strongest language.
- The experiment runner, invariant checker and data analysis are a natural fit for Python. Using one language for the lab and its tools keeps them together.
- Python libraries exist for building and validating ISO 20022 XML messages (to be evaluated in the Rails and ISO 20022 milestone).

## Consequences

The baseline stays in Ruby and is only run and tested, not extended. If a rail simulator later needs a Go library (for example moov-io/fednow20022), it can run as a separate service.
