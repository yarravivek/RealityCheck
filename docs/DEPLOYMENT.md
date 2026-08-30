# Deployment & Infrastructure Guide

## Live Production Topology

The public demo deployment uses Vercel for stateless FastAPI compute and Cloud Firestore for durable backend state in `asia-south1`.

`/api/health` identifies the compute/storage split, and the live workflow persists state transitions to Firestore in real time.

## Optional Containerized / Cloud Run Topology

### Services
- Container Runtime / Cloud Run
- Cloud Firestore in Native mode
- GenAI API / Structured LLM
- Pub/Sub & Cloud Scheduler for periodic obligation ticks

### Deploy Locally or to Cloud Container
```powershell
docker build -t realitycheck .
docker run --rm -p 8080:8080 realitycheck
```

Verify:
```powershell
Invoke-RestMethod "http://localhost:8080/api/health"
```
