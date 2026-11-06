# Postmortem Dataset

Structured records of public incidents in payment systems and the cloud infrastructure they depend on. This is the data for [Theme 1](../../research/01-outage-postmortems).

## Layout

- `incidents/` holds one YAML file per incident, named `YYYY-MM-DD-organization-short-name.yaml`.
- `_template.yaml` is the record format. Copy it to start a new record.

## Rules

1. Use primary sources: the organization's own postmortem or status page, a regulator or central-bank report, or a cloud provider's post-event summary.
2. Summarize in your own words. Do not paste postmortem text.
3. Record only what the source states. Put your own interpretation in `analysis_notes` and mark it as such.
4. Use `unknown` rather than guessing.
5. Each record must have at least one working source URL and the date you accessed it.

## Coding fields

The categories are draft version 0. They will be revised after the first 20–30 records, and every revision will be logged in this file.

| Field | Allowed values (v0) |
|---|---|
| `trigger` | `deploy`, `config-change`, `dependency-failure`, `capacity`, `network`, `datastore`, `hardware`, `security`, `human-operational`, `unknown`, `other` |
| `failing_layer` | `client`, `api-gateway`, `payment-service`, `ledger`, `message-broker`, `database`, `rail-or-scheme`, `cloud-provider`, `dns-or-identity`, `other` |
| `money_impact` | `none-reported`, `delayed`, `duplicated`, `missing`, `incorrect-balance`, `unknown` |
