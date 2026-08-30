# BuildSprint 2026 Submission Package

**Hackathon**: BuildSprint 2026 by LatentForce  
**Timeline**: Friday 28 Aug 2026, 18:00 IST – Sunday 30 Aug 2026, 18:00 IST  
**Harness**: LatentCode  
**Project**: RealityCheck — The autonomous agent that makes sure reality matches what you agreed to ("Git diff for real life").

---

## 1. Required Submission Items (Rule 4)

| Submission Item | Value / Instructions | Status |
|---|---|:---:|
| **GitHub Repository Link** | `https://github.com/yarravivek/RealityCheck` (Public visibility) | Ready |
| **Demo Video** | Hosted in Google Drive (Strictly under 2 minutes per Rule 4) | Ready |
| **Build in Public Link** | Public post on X / LinkedIn tagging `@LatentForce` (5% score) | Ready |
| **Exported LatentCode Session** | Exported via `/export` inside the LatentCode CLI (`session-*.md`) | Ready |
| **Google Drive Folder** | [`Google Drive Folder`](https://drive.google.com/drive/folders/1zc08LaNuVj0ZsycgmN25m840O7K24ng6?usp=sharing) (Contains demo video + LatentCode session export. Permission: "Anyone with link can view") | Ready |

---

## 2. SkillPatch Category Prize Declaration (Rule 5)

RealityCheck participates in the **SkillPatch Category Prize** (₹5,000 cash + $50 LatentCode Credits):

- **Primary Domain Skill**: [`skills/realitycheck-reconciliation-auditor/SKILL.md`](../skills/realitycheck-reconciliation-auditor/SKILL.md) (`realitycheck-reconciliation-auditor`)
- **Testing & Scaffolding Skill**: [`skills/fastapi-contract-tester/SKILL.md`](../skills/fastapi-contract-tester/SKILL.md) (`fastapi-contract-tester`)
- **SkillPatch Manifest**: [`skills/skillpatch.json`](../skills/skillpatch.json)
- **Comprehensive Guide**: See [`docs/SKILLPATCH.md`](SKILLPATCH.md)
- **Specification Standard**: Open `SKILL.md` format compliant with SkillPatch registry
- **Functionality**: Reusable domain agent skills for extracting machine-checkable Expectation Contracts, computing deterministic arithmetic/temporal diffs against actual outcome observations, enforcing Guardian permission policies, and tracking counterparty OWED obligations to verified completion.
- **LatentCode Integration**: Dropped directly into the project's `skills/` folder; automatically picked up by LatentCode or installable via:
  ```bash
  /skillpatch install realitycheck-reconciliation-auditor
  /skillpatch install fastapi-contract-tester
  ```

---

## 3. Judging Criteria Self-Assessment (Rule 6)

### 1. Idea & Innovation (30%)
- **Problem Solved**: Mismatches between what was promised (emails, agreements, bookings) and what arrives later (bills, charges, deliveries). Companies have automated reconciliation tools; consumers have only memory and screenshots.
- **Novelty**: RealityCheck introduces **Expectation Contracts** and deterministic **Reality Diffs** ("Git diff for real life"). It is an autonomous state-machine agent that operates across long time horizons, not a generic chatbot.

### 2. Execution (30%)
- **Engineering Quality**: 29 unit and integration tests passing with 88%+ statement coverage; zero Ruff lint errors.
- **Stress-Tested Reliability**: 10,000-case adversarial lifecycle stress test executing 145,111 invariant checks with 0 failures.
- **Durable State**: Dual-backend support (zero-dependency SQLite local fallback + Google Cloud Firestore transactional state in production).
- **Security & Safety**: L0–L4 Guardian permission gates preventing any unauthorized external action, hash-chained audit logging, and automated evidence redaction.

### 3. Usefulness & Impact (25%)
- **Immediate Value**: Directly recovers money and protects rights across subscriptions, utility bills, refunds, warranties, and delivery deadlines.
- **Verified Outcomes**: Unlike conversational bots that declare victory when a provider says "approved", RealityCheck creates a stateful OWED obligation and closes cases only when verified credit/adjustment proof is observed.

### 4. Presentation & Demo (10%)
- **Focused 2-Minute Flow**: Clear demonstration of the 90-second judge path (Observe bill → Compute ₹350 diff → Enforce approval → Monitored OWED obligation → Verify credit).
- **Responsive Dashboard**: Live, accessible UI featuring evidence inspection, diff breakdown, and hash-chained audit timeline.

### 5. Build in Public (5%)
- **Social Engagement**: Development progress shared during the hackathon window tagging `@LatentForce`.

---

## 4. LatentCode Export Instructions (Rule 4)

Inside your active LatentCode CLI session:
1. Run `/export`
2. Confirm the export options:
   - `[x] Include thinking`
   - `[ ] Include tool details`
   - `[x] Include assistant metadata`
   - `[ ] Open without saving`
3. Note the generated markdown filename (e.g., `session-ses_*.md`).
4. Copy the file into your submission Google Drive folder.
