# Release verification report

Verified on 30-08-2026 against the repository build and production runtime.

## Release gates

| Gate | Result | Evidence |
|---|---:|---|
| Static analysis | Pass | Ruff reports zero violations |
| Automated tests | Pass | 29 tests, 88.24% statement coverage |
| Adversarial lifecycle stress | Pass | 10,000 cases, 145,111 invariant checks, 0 failures |
| Concurrent HTTP sessions | Pass | 100 parallel full lifecycles, 0 failures |
| Duplicate/racing HTTP actions | Pass | 192 racing requests; 1 observation, 1 obligation, 1 recovery |
| Multi-process persistence | Pass | Independent store instances serialize atomic mutations |
| Container clean build | Pass | Python 3.12 slim image resolves from scratch |
| Container privilege | Pass | Runtime UID is the non-root `realitycheck` user |
| Repeated container boot | Pass | 10/10 two-worker starts healthy, 0 lock errors |
| Browser workflow | Pass | Observe, blocked action, approval, monitor, verify, reset |
| Lighthouse mobile | Pass | 100 Performance, 100 Accessibility, 100 Best Practices, 100 SEO |
| Live LLM extraction | Pass | Structured extraction with grounded terms and confidence scores |
| Dependency integrity | Pass | `pip check` reports no broken requirements |
| Secret scan | Pass | No provided API key or environment secret is tracked |

## Loss cases explicitly tested

- Provider contact before a material evidence-backed mismatch.
- Provider contact without one-attempt scoped approval.
- Verification before an obligation exists or before its deadline.
- Duplicate observations, approvals, obligations, and completion events.
- Matching credits that should explain rather than inflate a fee discrepancy.
- Missing terms and low-confidence evidence that must remain uncertain.
- Tampering with any earlier hash-chained audit event.
- Invalid or corrupt persisted state.
- Concurrent workers updating the same case.
- Provider timeout or invalid response creating a false obligation.
- Oversized evidence payloads and unauthenticated scheduler calls.
- Cross-user demo state leakage.

## Runtime truth

- The provider boundary is the explicitly labeled fictional FiberMax sandbox. No real company contact is claimed.
- The public deployment at `https://realitycheck-agent.vercel.app` uses Vercel for stateless FastAPI compute and Cloud Firestore for durable state. On 30-08-2026, `/api/health` reported `store: firestore`, location `asia-south1`, and `ai_configured: true`; a public extraction returned structured terms and the resulting case was persisted to Firestore.
- A live public lifecycle reached `recovered` with a ₹350 net difference, an approval-blocked action, one OWED obligation, and 12 audit events.

## Reproduce

```powershell
pip install -r requirements-dev.txt
ruff check app tests scripts
pytest --cov=app --cov-report=term-missing --cov-fail-under=85
python scripts/stress_test.py --cases 10000
docker build -t realitycheck .
docker run --rm -p 8080:8080 realitycheck
```
