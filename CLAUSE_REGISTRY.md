# MAOK Clause Registry

This document lists all normative clauses defined in MAOK v0.1.

Clauses are immutable once published.
They may only be explicitly deprecated in future versions.

---

## Clause Severity Levels

| Level | Meaning |
|------|--------|
| INFO | Informational, non-blocking |
| WARN | Warning, requires acknowledgment |
| FATAL | Immediate rejection, execution must stop |

---

## Registered Clauses

---

### MAOK-001-SEMANTIC-TRUTH

**Severity:** FATAL  

**Statement:**  
Market facts must not be implicitly booleanized, masked, or silently handled at the raw data layer.

**Rationale:**  
Flattening facts destroys adjudication integrity and makes replay impossible.

---

### MAOK-002-CA-ORDER-001

**Severity:** FATAL  

**Statement:**  
Corporate action adjustments must be applied before any tradability masking.

**Rationale:**  
Adjusting incomplete series introduces artificial smoothness and false profitability.

---

### MAOK-003-ENTROPY-GUARD

**Severity:** FATAL  

**Statement:**  
Cross-sectional operators must emit sample entropy metrics.  
If entropy falls below the policy-signed threshold, execution must be rejected.

**Rationale:**  
Low-entropy signals indicate statistical collapse and cannot be legitimized by computation.

---

## Clause Evolution Rules

- Clauses may be **deprecated**, never silently altered
- Deprecation must include:
  - explicit reason
  - replacement clause (if any)
- Historical AuditTrace must remain replayable under original clauses

---

## End of Registry
