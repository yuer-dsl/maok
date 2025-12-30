# NOTICE

## Legal & Architectural Notice

MAOK (Market Adjudication & Operational Kernel) is a **charter-level specification**.

This repository defines:
- adjudication principles
- semantic constraints
- audit and replay contracts

It does **NOT** provide:
- execution engines
- performance implementations
- trading systems
- AI models
- optimization logic

---

## Non-Acceleration Notice

MAOK is **not designed to accelerate decision-making**.

Any system claiming MAOK compliance for:
- faster execution
- higher returns
- improved alpha
- reduced latency

without enforcing **fail-closed adjudication**, **replayable audit**, and **physical veto authority**  
is **misrepresenting MAOK**.

---

## Non-Bypass Requirement

Any implementation that:
- allows execution when MAOK adjudication fails
- logs rejection without enforcing termination
- treats MAOK as advisory rather than mandatory

**is not MAOK-compliant**.

---

## No Implicit Endorsement

Publishing this specification does not grant:
- production readiness
- regulatory approval
- safety guarantees
- commercial authorization

MAOK defines **responsibility boundaries**, not operational fitness.

---

## Interpretation Authority

Semantic interpretation of this specification follows:
1. Explicit clauses in RFC documents
2. Clause Registry definitions
3. Recorded AuditTrace replay rules

Silence does not imply permission.

---

## Closing

MAOK exists to define **when systems must stop**.

Any system unwilling to stop  
is not operating under MAOK.
