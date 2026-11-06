# Development Log

A dated record of what was done, what failed and what was decided. Only things that actually happened go here. Newest entries first.

## 2026-11-05

- Created the repository with the research structure: four theme folders, the postmortem dataset format, the experiment template, issue templates and the roadmap.
- Imported `lab/baseline` from brandur/rocket-rides-atomic at commit `94b370d` as a file snapshot. Left out the upstream `.env` and replaced the Stripe test key in `spec/spec_helper.rb` with a placeholder, so no API keys are committed. Changes are listed in `lab/baseline/UPSTREAM.md`.
- Recorded three decisions: [ADR 0001](adr/0001-single-repository.md) (one repository for all themes), [ADR 0002](adr/0002-baseline-as-reference-system.md) (baseline kept as a reference system), [ADR 0003](adr/0003-python-for-payments-lab.md) (Python for payments-lab).
- Not yet done: the baseline has not been run, and its tests have not been executed in this repository.
