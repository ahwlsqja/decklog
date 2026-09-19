# Open research questions

Decklog's central question: **what state, context, progress, and responsibility must persist — outside any single execution agent — for a newly spawned agent to continue a piece of incident work correctly?**

These are open questions, not results. Status: research stage — nothing here is implemented or evaluated.

## Hypotheses under study

- Central LLM orchestration may incur avoidable handoff cost: each step re-serializes context through the coordinator, which also becomes a dependency for continuity.
- A durable shared history plus short-lived agents that reconstruct only the context their task needs may reduce that dependency — or shorter lifetimes may instead raise reconstruction cost. Break-even is an empirical question; neither direction is proven.
- Decentralization is an option to evaluate, not a claimed benefit. The comparison itself is the experiment.

## Questions

### 1. Minimal sufficient record

Which fields — goal, constraints, decisions, pending obligations, evidence pointers — must an entry carry so a fresh agent can continue within **task-defined acceptable-continuation criteria**?

Model outputs legitimately differ and several next actions may be valid. The target is preserved constraints, evidence, and unfinished obligations — *not* identical behavior to a continuously running agent, and not identical next actions from the same model.

### 2. Reconstruction cost vs. lifetime

How does rehydration cost grow as agent lifetime shrinks, and where is break-even against holding a long-lived orchestrator context?

The dependency/cost benefits of the log-based design are hypotheses, not established results — shorter lifetimes may raise reconstruction cost rather than reduce total cost.

### 3. Concurrent writers and external effects

Under N:M collaboration, what combined contract — log consumption, ownership of pending actions, commit rules — prevents two agents from double-executing an external effect or silently forking responsibility? Where must tool-side idempotency or result reconciliation take over?

Ordering in the log alone does not guarantee correctness of external effects: a recorded order is not ownership of the side effect.

### 4. Chosen observations

If observations are actions selected from reconstructed context (not a passive feed), how do we detect when a fresh agent observes the wrong thing because reconstruction dropped relevant state?

## Planned evaluation axes

Coordination strategy and execution lifetime vary as **independent axes**. Candidate coordination strategies:

1. Durable centralized LLM orchestration
2. Rule-based dispatch over the shared history
3. N:M consumer-driven coordination

Agent lifetime varies where applicable, with persistence, tools, model, and task conditions held comparable across arms. Domain: SRE incident/ticket scenarios. Planned metrics: correct-continuation rate after agent replacement or suspension; tokens/context bytes per completed unit of work; duplicate or contradictory external actions; recovery behavior under injected faults.

No final experimental design is selected; everything above is a plan, not a claim.

## Discussion

Comment or propose refinements via [GitHub issues](https://github.com/ahwlsqja/decklog/issues). See [../related-work.md](../related-work.md) for the prior work these questions must be compared against.
