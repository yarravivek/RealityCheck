---
name: realitycheck-reconciliation-auditor
description: Audits expectation contracts against actual bills/receipts, computes deterministic reality diffs, and validates counterparty resolution evidence with strict zero-hallucination verification.
---

# RealityCheck Reconciliation Auditor (SkillPatch Skill)

This skill equips LatentCode and compatible agents with domain-specific procedures for ingesting agreements, computing deterministic reality diffs against actual outcome observations, enforcing user consent gates, and tracking counterparty obligations to verified completion.

## When to Use This Skill

Activate this skill when:
1. Compiling unorganized consumer agreements (emails, receipts, pricing tables, warranties, delivery estimates) into machine-verifiable **Expectation Contracts**.
2. Analyzing subsequent invoices, bank charges, shipment confirmations, or merchant responses against active expectations.
3. Calculating mathematical and temporal discrepancies between promised terms and actual observed states.
4. Structuring L0–L4 consent escalation packets for the Guardian agent before initiating counterparty contact.
5. Tracking newly received counterparty promises (e.g., "we will credit ₹350 within 48 hours") as stateful **OWED obligations**.

---

## Reconciliation Workflow

### Step 1: Expectation Extraction & Grounding
When presented with source text from an agreement:
- Extract discrete, measurable commitments (pricing, recurrence intervals, promised inclusions, deadlines, warranty periods).
- Hash the raw evidence string using SHA-256 (`evidence_hash`).
- Require an exact textual quote from the source document for every term.
- Assign an extraction confidence score between `0.0` and `1.0`. Any term with confidence below `0.75` MUST be flagged as uncertain and cannot authorize automated dispute actions.

### Step 2: Deterministic Reality Diff
When an observation (e.g., subsequent bill or delivery receipt) arrives:
- Separate semantic understanding from arithmetic.
- Compare baseline contract values against actual observed values:
  $$\Delta = \text{Actual} - \text{Expected}$$
- Classify the discrepancy into one of three categories:
  - **Legitimate Variation**: Discrepancy is accounted for by documented proration, applicable sales taxes, user-approved plan changes, or promotional phase transitions.
  - **Unexplained Mismatch**: Actual cost exceeds agreed rate or agreed inclusion is billed separately without contractual basis.
  - **Uncertain / Incomplete**: Insufficient evidence to establish discrepancy validity.

### Step 3: Guardian Policy & Permission Enforcement
Before drafting or triggering any external communication:
- Verify authorization level against the system consent matrix:
  - **L0 (Autonomous Read-Only)**: Parse documents, compute diffs, evaluate rules.
  - **L1 (Internal Notice)**: Alert user on dashboard.
  - **L2 (Routine Action - Scoped Approval Required)**: Draft and send single-attempt counterparty clarification or credit request. Requires explicit, non-delegated user approval.
  - **L3 / L4 (High-Risk - Strictly Prohibited Autonomously)**: Legal demands, binding settlements, subscription cancellations, or regulatory complaints.
- Ensure all outbound packets include:
  - Exact citation of original promise with timestamp and source hash.
  - Line-item breakdown of the observed difference.
  - Deterministic expected adjustment figure.

### Step 4: Stateful OWED Obligation Tracking
When a counterparty responds with an approval or promise:
- **Do not mark the case as resolved.** A promise to correct is not proof of correction.
- Spawn a monitored **OWED obligation** containing:
  - Target amount or deliverable.
  - SLA deadline timestamp.
  - Verification condition (e.g., next billing statement or bank credit credit note).
- Transition case status to `monitoring`.

### Step 5: Independent Outcome Verification
- When subsequent evidence (e.g., adjustment credit notice or corrected bill) arrives:
  - Re-run the diff engine against the initial deficit.
  - Verify that the credited amount exactly matches or exceeds the disputed sum.
  - Only when fresh, hashed evidence confirms the credit, transition case status to `recovered`.
  - Log the completed event in the append-only, hash-chained audit ledger.

---

## Verification Checklist for LatentCode Sessions

- [ ] All numeric comparisons are computed deterministically (no LLM arithmetic).
- [ ] Every extracted term contains an exact source quote and SHA-256 hash.
- [ ] No outbound provider contact occurs without explicit user approval.
- [ ] Cases remain open in `monitoring` until empirical proof of correction arrives.
- [ ] Zero unverified closures.
