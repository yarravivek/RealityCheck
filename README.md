<div align="center">

# RealityCheck

### The autonomous agent that makes sure reality matches what you agreed to.

**It is Git diff for real life.**

[![CI](https://github.com/yarravivek/RealityCheck/actions/workflows/ci.yml/badge.svg)](https://github.com/yarravivek/RealityCheck/actions/workflows/ci.yml)
[![BuildSprint 2026](https://img.shields.io/badge/BuildSprint-2026-6C5CE7?style=flat)](https://github.com/yarravivek/RealityCheck)
[![Built with LatentCode](https://img.shields.io/badge/Harness-LatentCode-00B894?style=flat)](https://latentstack.dev)
[![SkillPatch](https://img.shields.io/badge/SkillPatch-Compatible-FD79A8?style=flat)](skills/realitycheck-reconciliation-auditor/SKILL.md)
![Python 3.11+](https://img.shields.io/badge/Python-3.11%2B-1e5948)
![Cloud Firestore](https://img.shields.io/badge/Google_Cloud-Firestore-4285F4)

[Live demo](https://realitycheck-agent.vercel.app) · [Architecture](docs/ARCHITECTURE.md) · [2-minute demo video](https://drive.google.com/drive/folders/1zc08LaNuVj0ZsycgmN25m840O7K24ng6?usp=sharing) · [Build in Public](https://lnkd.in/p/dPxTwKBM)

</div>

---

![RealityCheck product dashboard](docs/dashboard.png)

## The failure RealityCheck prevents

The promise is in an email. The charge appears two months later. The correction is promised in support chat. The credit may arrive after another billing cycle. Consumers do not lose because the evidence is absent; they lose because nobody continuously reconciles those events.

Companies have reconciliation systems to catch what does not match. Consumers have memory and screenshots.

RealityCheck gives an individual an evidence-backed expectation ledger and an autonomous agent that closes the loop:

> **Expectation → Observation → Reality Diff → Judgment → Resolution → Verified outcome**

When you buy, book, subscribe, or receive a measurable promise, RealityCheck compiles the agreement into an **Expectation Contract**. Later, it observes the invoice, delivery, refund, or provider response; computes what changed; separates legitimate variation from unexplained mismatch; and — within your permissions — pursues the correction until reality matches the agreement.

## The 90-second judge path

1. Open the dashboard. FiberMax promised **₹499/month for 12 months, installation free**.
2. Click **Observe next bill**. The agent parses a new ₹849 invoice and deterministically isolates a **₹350 installation fee**.
3. Inspect the exact welcome-email evidence and the Judge Agent's explanation.
4. Approve one scoped provider contact. The Guardian blocks the action until approval is explicit.
5. FiberMax promises a ₹350 credit within 48 hours. RealityCheck creates a new OWED obligation instead of declaring victory.
6. Fast-forward the demo. The case closes only after a new statement proves that the ₹350 credit arrived.

The final screen reads **₹350 RECOVERED** while the user's manual messages, document searches, and remembered follow-ups remain zero.

![RealityCheck system architecture](docs/architecture.svg)

## Why this is agentic, not a chatbot

RealityCheck owns a long-running goal and state machine. It decides when to wait, when to observe, which differences deserve action, which actions require approval, and when evidence is sufficient to close the case.

| Agent | Responsibility | Durable output |
|---|---|---|
| Expectation Agent | Extract evidence-backed measurable promises | Expectation Contract |
| Watch Agent | Wake at deadlines or expected observations | Scheduled watch item |
| Observation Agent | Parse bills, messages, receipts, and outcomes | Actual State |
| Diff Agent | Compare numbers, dates, inclusions, and specs | Reality Diff |
| Judge Agent | Separate legitimate, unexplained, and uncertain variation | Evidence-backed judgment |
| Resolution Agent | Prepare the least-risk permitted correction | Action + evidence packet |
| OWED Agent | Turn new provider promises into monitored obligations | Deadline + verification rule |
| Guardian Agent | Enforce consent and prohibit sensitive autonomous actions | Policy decision + audit record |
| Outcome Agent | Verify the correction before closing | Recovered value + proof |

## SkillPatch Category Integration (Rule 5)

RealityCheck ships with first-class SkillPatch skills built on the open `SKILL.md` standard, qualifying for the **₹5,000 + $50 Credits SkillPatch Category Prize**:

- **Core Domain Skill**: [`realitycheck-reconciliation-auditor`](skills/realitycheck-reconciliation-auditor/SKILL.md) — Teaches LatentCode agents how to audit multi-party consumer contracts, compute deterministic numeric and date diffs, apply L0–L4 Guardian permission policies, and track counterparty commitments as stateful OWED obligations.
- **Testing & Scaffolding Skill**: [`fastapi-contract-tester`](skills/fastapi-contract-tester/SKILL.md) — Scaffolds adversarial lifecycle stress suites and invariant tests.
- **SkillPatch Manifest**: [`skills/skillpatch.json`](skills/skillpatch.json)
- **Integration Guide**: [`docs/SKILLPATCH.md`](docs/SKILLPATCH.md)
- **SkillPatch CLI**: Installable into any LatentCode session via:
  ```bash
  /skillpatch install realitycheck-reconciliation-auditor
  /skillpatch install fastapi-contract-tester
  ```

## BuildSprint 2026 Judging Criteria Alignment

| Criterion | Weight | RealityCheck Execution & Proof |
|---|---:|---|
| **Idea & Innovation** | 30% | First autonomous personal reconciliation agent. Replaces disjointed memory and screenshots with an evidence-backed expectation ledger and deterministic reality diffs ("Git diff for real life") rather than another conversational chatbot. |
| **Execution** | 30% | 29 automated tests (88.24% statement coverage), 10,000-case adversarial stress tests with 145,111 invariant checks and 0 failures. Dual-backend persistence (zero-dependency SQLite local + Cloud Firestore transactional production). |
| **Usefulness & Impact** | 25% | Solves real consumer money loss across subscription hikes, utility errors, phantom fees, missed refunds, and delivery deadlines. Converts provider responses into stateful OWED obligations, closing only on verified recovery. |
| **Presentation & Demo** | 10% | Clean, responsive UI with zero-config deterministic sandbox demo, live inspection of contract diffs, OWED monitoring, and recovered evidence within a tight 90-second judge flow. |
| **Build in Public** | 5% | Public build updates and launch announcement shared during the hackathon window: [LinkedIn Post](https://lnkd.in/p/dPxTwKBM) (tagging `@LatentForce`). |

## What is real and what is sandboxed

Truth labeling is a product feature, not a footnote.

- **Real:** the FastAPI state machine, executable agent fleet, LLM structured extraction path, deterministic diff engine, evidence hashing/redaction, consent gate, OWED obligation, atomic SQLite/Firestore transitions, Firestore-backed public runtime, scheduler endpoint, hash-chained audit log, and tests.
- **Live in production:** Structured semantic extraction through GenAI SDK. The public health endpoint reports `ai_configured: true`; the UI exposes the connected model instead of hiding runtime status.
- **Provider sandbox:** FiberMax is a fictional, deterministic connector used so a public judging demo never contacts or harasses a real company. The action packet, connector call, reply, obligation, and verification are real application behavior; only the external counterparty is sandboxed and labeled.

## Core Technologies

- **LatentCode** — AI coding harness for rapid iterative development and verified session transcripts.
- **SkillPatch** — Reusable agent skill standard (`skills/realitycheck-reconciliation-auditor`).
- **Structured GenAI** — Semantic extraction and evidence-grounded contract reasoning.
- **Specialist Agent Fleet** — Autonomous multi-agent coordination and orchestration boundaries.
- **Cloud Firestore / SQLite** — Durable cross-session case, expectation, obligation, and audit state.
- **FastAPI & Pydantic** — Strongly typed state machine, validation, and deterministic diff engine.

## Run locally

The public judge demo is available at <https://realitycheck-agent.vercel.app>. FastAPI compute
runs on Vercel and durable transactional state runs in the default Cloud Firestore database
(`asia-south1`). The health endpoint exposes this split
topology explicitly. The provider connector remains an honestly labeled deterministic sandbox.

### Prerequisites

- Python 3.11+
- An LLM API key (optional for deterministic demo; required for live extraction)

### Windows PowerShell

```powershell
git clone https://github.com/yarravivek/RealityCheck.git
Set-Location RealityCheck
py -m venv .venv
.\.venv\Scripts\Activate.ps1
pip install -r requirements-dev.txt
Copy-Item .env.example .env
# Edit .env and set GOOGLE_API_KEY. Never commit .env.
uvicorn app.main:app --reload --port 8080
```

Open <http://localhost:8080>. API docs are at <http://localhost:8080/api/docs>.

### macOS / Linux

```bash
git clone https://github.com/yarravivek/RealityCheck.git
cd RealityCheck
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements-dev.txt
cp .env.example .env
uvicorn app.main:app --reload --port 8080
```

The deterministic end-to-end demo works without a key. This is deliberate graceful degradation, and the UI never labels that mode as live AI.

## Safety model

- Evidence sources are connected explicitly by the user.
- Every structured term retains its source hash, quote, and span.
- Uncertainty is preserved; conflicting or missing evidence is never invented away.
- Routine provider contact requires granted L2 permission and scoped approval.
- Settlements, purchases, plan changes, rights waivers, legal claims, and regulatory complaints are blocked without explicit approval.
- Provider contact is rate-limited by design and stops when permission is revoked.
- The product uses neutral language such as “unexplained” rather than alleging fraud.
- Secrets, local evidence, databases, and generated uploads are gitignored.

See [SECURITY.md](SECURITY.md) for threat boundaries and reporting.


## License

MIT. See [LICENSE](LICENSE).
