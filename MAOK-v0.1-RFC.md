# MAOK v0.1 RFC

**Market Adjudication & Operational Kernel**
**Status:** Draft / Charter-Level
**Scope:** Specification Only (Non-Executable)

---

## 0. Abstract

MAOK (Market Adjudication & Operational Kernel) is a **charter-level specification** designed to introduce **deterministic adjudication, replayable audit, and fail-closed compliance** into quantitative and AI-driven decision systems.

MAOK provides **no execution engine, no model, and no performance implementation**.
Its sole purpose is to decide **whether a system is allowed to proceed** before an irreversible decision is executed.

---

## 1. Motivation

Modern quantitative and AI systems suffer from structural failures that cannot be fixed by better models or faster computation:

1. **Results are prioritized over responsibility**
   Systems optimize for output quality, not for decision legitimacy.

2. **Logs are mistaken for evidence**
   Traditional logs cannot prove *why* a decision was allowed or rejected.

3. **Decisions are not replayable**
   Backtest–live discrepancies cannot be adjudicated at the system level.

4. **Implicit open-world assumptions**
   Systems assume execution is allowed unless explicitly blocked.

MAOK exists to **terminate these assumptions at the architectural level**.

---

## 2. Design Principles

### 2.1 Fail-Closed by Default

> **If a decision cannot prove its own legitimacy, it must be rejected.**

There is no implicit “pass” path in MAOK.

---

### 2.2 Adjudication Before Computation

All operators and signals must undergo **semantic and factual adjudication**
before any computation result is considered valid.

Computation itself does not imply legitimacy.

---

### 2.3 Replayability Equals Legitimacy

Any MAOK decision (ACCEPT or REJECT) must be:

* Replayable with the same fact snapshot
* Using the same clause set
* Under the same policy signature
* Producing the identical verdict

Failure to replay indicates **systemic invalidity**.

---

## 3. Core Concepts

### 3.1 Market Fact

Market facts are **non-boolean states** that must never be flattened at the data layer, including but not limited to:

* Trading suspension
* Limit-up / limit-down
* No quotation
* Data missing

Facts may be adjudicated — never erased.

---

### 3.2 Tradability

Tradability is **not a data attribute**.
It is an **adjudicated outcome** determined by clauses and policy signatures.

---

### 3.3 Clause

A Clause is MAOK’s smallest legal unit.
Each clause defines:

* How facts are interpreted
* Under which conditions execution must be rejected
* The severity level of the verdict

---

## 4. Normative Clauses

### MAOK-001-SEMANTIC-TRUTH

**Market facts must not be implicitly booleanized or silently handled at the raw data layer.**

---

### MAOK-002-CA-ORDER-001

**Corporate action adjustments must be applied before any tradability masking.**

Any adjustment applied on masked or incomplete series must be rejected or flagged as severe financial deviation risk.

---

### MAOK-003-ENTROPY-GUARD

**Cross-sectional operators must emit sample entropy metrics.**

If entropy falls below the policy-signed threshold,
the system must reject downstream signal generation.

---

## 5. Audit & Evidence Model

### 5.1 AuditTrace

An `AuditTrace` is MAOK’s **legal evidence unit** and must contain:

* Operator ID and version
* Self-contained fact snapshot
* Policy signature hash
* Triggered clause IDs
* Decision and severity
* UTC timestamp

---

### 5.2 Replay Contract

Every AuditTrace must satisfy:

```
replay(facts, clauses, operator_version) -> identical decision
```

Any divergence indicates:

* Semantic drift
* Non-deterministic implementation
* Or unauthorized rule mutation

---

## 6. Compliance Gateway Model

MAOK must be positioned as a **non-bypassable gate**:

```
Signal Generation → MAOK Gateway → Execution
```

Gateway enforcement rules:

* `REJECT` must physically terminate execution
* Rejection must persist AuditTrace
* Any execution bypassing the gateway is invalid by definition

---

## 7. Non-Goals

MAOK explicitly does **not** address:

* Performance optimization
* Alpha generation
* Model training
* Data engineering
* Execution algorithms

These belong to other system layers.

---

## 8. Relationship to EDCA OS (Informative)

Within EDCA OS, MAOK is positioned as a:

> **Charter-Level Adjudication Kernel**

* EDCA governs expression, cognition, and decision paths
* MAOK governs **whether such paths are permitted to exist**

MAOK does not replace EDCA.
It holds veto authority over EDCA outcomes.

---

## 9. Versioning & Evolution

* v0.1 defines the minimal adjudication charter
* Future versions may:

  * Append new clauses
  * Explicitly deprecate clauses
* Silent semantic changes are prohibited

---

## 10. Closing Statement

MAOK is not designed to make systems smarter.
It is designed to make systems **honest under uncertainty**.

A system that can reject an invalid decision *at the moment it occurs*,
rather than explain failure afterward,
is the minimum requirement for operating in the real world.


