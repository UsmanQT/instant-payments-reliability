# Upstream provenance

| | |
|---|---|
| Upstream | https://github.com/brandur/rocket-rides-atomic |
| Commit | `94b370ddbdc8d08fb263f07c221bab42190d48e6` (2022-12-01) |
| License | MIT (see `LICENSE` in this folder) |
| Author | Brandur Leach |
| Imported | 2026-11-05 as a file snapshot; upstream git history is not included |
| Related article | Brandur Leach, "Implementing Stripe-like Idempotency Keys in Postgres", https://brandur.org/idempotency-keys |

## Why it is here

This is the **reference system** for Theme 2. It implements idempotency keys, atomic phases with recovery points, a completer, a transactionally staged job queue and a key reaper around an external charge that cannot be rolled back. Experiments in this project test how that design behaves under faults. See [ADR 0002](../../docs/adr/0002-baseline-as-reference-system.md).

## Changes from upstream

Keep this list complete. Every change to files in this folder must be recorded here.

| Date | File | Change | Reason |
|---|---|---|---|
| 2026-11-05 | `.env` | Not imported; replaced with `.env.example` | The upstream file contains a Stripe test API key. Secrets, even test ones, are not committed here |
| 2026-11-05 | `spec/spec_helper.rb` | Stripe test key replaced with `sk_test_placeholder` | Same reason. Specs that call Stripe for real will need stripe-mock (tracked as an issue) |
| 2026-11-05 | `UPSTREAM.md`, `.env.example` | Added | Provenance and configuration example |

## Known state at import (not yet verified)

- Upstream CI was Travis CI with Ruby 2.4.2 and PostgreSQL 9.6. It has not been run in this repository yet.
- `Gemfile.lock` is from upstream and probably needs updating for current Ruby.
