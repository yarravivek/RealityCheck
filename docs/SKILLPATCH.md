# SkillPatch Integration Guide — BuildSprint 2026

RealityCheck is fully integrated with **SkillPatch** (`https://skillpatch.dev`), the open skill registry for AI coding agents, qualifying for the **BuildSprint 2026 SkillPatch Category Prize** (₹5,000 cash + $50 LatentCode Credits).

---

## 1. Overview & Category Prize Qualification (Rule 5)

Per **Rule 5** of the BuildSprint 2026 Official Rulebook:
> *"Use at least one Skill from SkillPatch in your build to qualify for this category, and name the skill or skills you used on the submission form. Undeclared use may not be counted. Prize: ₹5,000 cash + $50 LatentCode Credits."*

RealityCheck incorporates **two SkillPatch packages** conforming to the open `SKILL.md` standard, managed via the `skills/` directory and [`skills/skillpatch.json`](../skills/skillpatch.json).

---

## 2. Installed Skills in RealityCheck

### Skill 1: `realitycheck-reconciliation-auditor` (Domain Core)
* **Location**: [`skills/realitycheck-reconciliation-auditor/SKILL.md`](../skills/realitycheck-reconciliation-auditor/SKILL.md)
* **Slug**: `realitycheck-reconciliation-auditor`
* **Version**: `1.0.0`
* **Purpose**: Teaches LatentCode and autonomous agents how to:
  1. Extract structured, evidence-backed **Expectation Contracts** from unstructured consumer agreements (emails, invoices, receipts).
  2. Compute deterministic mathematical and temporal **Reality Diffs** against incoming observations.
  3. Enforce **Guardian L0–L4 permission gates** to prevent unauthorized outbound counterparty contact.
  4. Convert counterparty promises into stateful **OWED obligations**.
  5. Close cases strictly upon independent empirical proof of resolution.

### Skill 2: `fastapi-contract-tester` (Scaffolding & Quality Gate)
* **Location**: [`skills/fastapi-contract-tester/SKILL.md`](../skills/fastapi-contract-tester/SKILL.md)
* **Slug**: `fastapi-contract-tester`
* **Version**: `1.2.0`
* **Purpose**: Scaffolds adversarial lifecycle stress tests and pytest invariant assertions, enabling RealityCheck's 10,000-case / 145,111 invariant verification suite.

---

## 3. How SkillPatch Integrates with LatentCode

1. **Native Directory Discovery**:
   LatentCode automatically scans the root `skills/` directory at startup and indexes all valid `SKILL.md` packages.

2. **Skill Installation via LatentCode CLI**:
   Skills can be fetched dynamically inside an active LatentCode session:
   ```bash
   /skillpatch install realitycheck-reconciliation-auditor
   /skillpatch install fastapi-contract-tester
   ```

3. **Publishing / Saving Reusable Skills**:
   ```bash
   /skillpatch save
   ```
   Packages and security-reviews the skill directly for the SkillPatch public registry.

---

## 4. Copy-Paste Submission Declaration for Rule 5

When filling out the BuildSprint submission form:

* **Did you use SkillPatch?**: `Yes`
* **Skill Name**: `realitycheck-reconciliation-auditor` (and `fastapi-contract-tester`)
* **Explanation**:
  > *"We developed and integrated the 'realitycheck-reconciliation-auditor' SkillPatch skill (built on the open SKILL.md specification). It provides our LatentCode agent with domain-specific procedures to extract machine-checkable Expectation Contracts, calculate deterministic numeric and date reality diffs against incoming bills/receipts, enforce Guardian consent gates, and monitor counterparty commitments as stateful OWED obligations until independently verified. We also utilized 'fastapi-contract-tester' for automated invariant and lifecycle test scaffolding."*
