# maok
MAOK (Market Adjudication &amp; Operational Kernel) is a charter-level specification for deterministic audit, semantic adjudication, and fail-closed compliance in quantitative and AI-driven systems.  This repository publishes the MAOK charter, RFCs, and audit protocols only. No execution engine, model, or performance implementation is included.
# MAOK

**MAOK — Market Adjudication & Operational Kernel**

MAOK is not a quantitative library, an AI framework, or an optimization engine.

MAOK is a **charter-level adjudication specification** that defines how decisions are allowed to exist, be audited, and be rejected in production-grade quantitative and AI-driven systems.

---

## What MAOK Is

MAOK defines:

- How *market facts* must be represented without semantic erosion
- How *operator decisions* are adjudicated against explicit clauses
- How *audit traces* must be replayable, deterministic, and non-repudiable
- How systems must **fail closed** when correctness cannot be proven

MAOK treats decision-making as a **legal process**, not a statistical convenience.

---

## What MAOK Is Not

MAOK does **not** provide:

- Alpha generation
- Signal optimization
- Performance tuning
- Backtesting tricks
- Execution strategies

If your goal is to be faster, smarter, or more profitable, MAOK will not help you.

If your goal is to ensure that a decision is **allowed to exist**, MAOK is the final gate.

---

## Core Principles

1. **Facts Are Not Booleans**  
   Market conditions such as suspension, limit-up, or missing data are treated as *case facts*, not flags to be silently ignored.

2. **Adjudication Precedes Computation**  
   No calculation is permitted before semantic adjudication against declared clauses.

3. **Fail-Closed by Default**  
   If a decision cannot prove its legitimacy, it must be rejected.

4. **Audit Is Replayable**  
   Every rejection or approval must be reproducible from its recorded facts, clauses, and operator identity.

5. **Responsibility Is Non-Transferable**  
   Decisions cannot be justified post hoc. If they pass, they pass with a trace. If they fail, they fail with evidence.

---

## Repository Scope

This repository intentionally publishes only:

- The MAOK charter (RFC)
- Type-level specifications
- Audit and replay protocols
- Non-executable reference structures

**Execution engines, gateways, and enforcement logic are explicitly out of scope.**

---

## Status

MAOK is currently in **v0.1 — Charter Phase**.

This phase focuses on:
- Semantic correctness
- Adjudication determinism
- Institutional accountability

Not on speed, convenience, or adoption.

---

## Closing Statement

> MAOK does not help you make money.  
> It decides whether your money-making logic is allowed to exist.

