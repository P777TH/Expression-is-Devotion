---
title: Graph-First Option
description: Property graph as the primary domain store, evaluated against current product needs
---

## Summary

A property graph represents people, organisations, missions, artworks, gifts,
testimonies, and their relationships as nodes and edges. It can make questions
about multi-hop connections and network structure natural to express.

## Potential Value

* Explore mission and supporter networks or trace impact relationships.
* Discover relationships that are awkward to express in a fixed report.
* Provide a natural visual exploration model for analysts.

## Risks to Validate

* Demonstrate the required financial transaction, constraint, authorization,
  audit, backup, and reporting behavior with the selected graph technology.
* Avoid coupling the payment authority model to graph-specific traversal needs.
* Account for specialist skills, operational tooling, and migration/exit costs.

## Decision Gate

Keep graph-first as a separate option. Reconsider only if graph traversal is a
critical business workflow and a technical spike proves the financial, privacy,
and operations controls. Otherwise assess a derived read model in the
[hybrid option](../hybrid/README.md).