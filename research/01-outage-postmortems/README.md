# Theme 1: Why Payment Systems Fail in the Cloud

**Status:** Not started · Milestone: Postmortem dataset v1

## Research question

What failure patterns recur in public postmortems of payment systems and the cloud infrastructure they run on, and which architectural weaknesses do they expose?

## Sub-questions

1. Which failure triggers are most common: deploys and configuration changes, dependency failures, capacity, network, data stores, or other?
2. How often does a failure spread from a shared dependency (cloud region, DNS, identity, database) into payment processing?
3. In how many incidents did money end up in an uncertain state (duplicates, missing payments, delayed settlement)? How was it reconciled?
4. Which failures could be reproduced in a lab, and which could not?

## Method

1. Collect public, first-party sources: company postmortems and status-page incident reports, regulator and central-bank reports, cloud provider post-event summaries.
2. Code each incident with the schema in [`datasets/postmortems`](../../datasets/postmortems): trigger, failing layer, failure class, detection, recovery, money impact, and source.
3. Build the taxonomy from the coded data, not before it.
4. Map each failure class to a reproducible scenario in `lab/`. This mapping links Theme 1 to Themes 2–4.

## Inclusion rules

- Primary sources only. News articles may point to a source but are not themselves the source.
- Record only what the source says. Mark inferences as inferences.
- Store links and short factual summaries in your own words; never copy postmortem text into the repository.

## Prior work to read first

See [reading notes](../reading-notes). Start with Gunawi et al., "Why Does the Cloud Stop Computing?" (SoCC 2016), which is the closest existing large-scale study of cloud outages.

## Findings

None yet.
