---
title: Relational and Graph Hybrid Option
description: Relational system of record with a derived graph projection for later relationship analysis
---

## Summary

Keep payments, approvals, consent, and canonical records in the relational
source of truth. Publish selected mission, organisation, artist, artwork,
testimony, and funding relationships into a graph projection only when a
measured use case needs graph traversal.

## Benefits and Costs

This preserves transactional ownership while enabling network analysis. It
also introduces eventual consistency, projection rebuilds, duplicated data,
monitoring, and data-deletion propagation. The projection must never authorize
or execute a payout.

## Implementation Guardrails

* Do not dual-write the database and graph in a request path.
* Use a replayable change feed or transactional outbox and make processing
  idempotent.
* Define freshness objectives, rebuild procedures, alerts, access-control
  propagation, and deletion handling.
* Keep sensitive financial details out of the projection unless approved.

## Decision Gate

Defer until a named user need and representative queries show that relational
queries are insufficient. Compare complexity, latency, freshness, and total
operating cost before adding another store.