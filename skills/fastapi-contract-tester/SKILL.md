---
name: fastapi-contract-tester
description: Scaffolds pytest test cases for FastAPI stateful lifecycle transitions, invariant assertions, and deterministic reconciliation diffs.
---

# FastAPI Contract & Lifecycle Tester (SkillPatch Skill)

This skill provides LatentCode and compatible coding agents with testing patterns and automated assertions for stateful FastAPI reconciliation agents.

## Purpose

Automates the generation and execution of:
1. Deterministic arithmetic invariant tests (e.g. ensuring no floating point drift and exact discrepancy isolation).
2. Permission gate enforcement tests (ensuring Guardian blocks unauthorized outbound transitions).
3. State machine lifecycle tests (Expectation → Observation → Diff → Monitored OWED → Verified Recovery).
4. Dual-backend store consistency tests (SQLite and Cloud Firestore equivalence).

## Usage in LatentCode

When running test scaffolding or verifying agent integrity:
```powershell
# Run full suite with coverage
python -m pytest --cov=app --cov-report=term-missing --cov-fail-under=85

# Run adversarial lifecycle stress harness
python scripts/stress_test.py --cases 10000
```
