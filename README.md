# DevOps Journey — Omar Emam

Cloud Systems Engineer (Azure · AZ-104, SC-300, MS-102) building DevOps skills end to end: Linux → containers → cloud → IaC → CI/CD → observability, followed by certifications.

This repo tracks everything: the roadmap, each stage's tasks and solutions, and a daily progress log.

---

## Roadmap & progress

Planned dates are estimates. They're recalibrated at the end of every stage based on real pace (see [progress-log.md](progress-log.md)).

| # | Stage | Study (days) | Planned finish | Actual finish | Status |
|---|---|---|---|---|---|
| 1 | Linux Admin 1 | 12–18 | — | done | ✅ |
| 2 | Bash Scripting | 2–4 | — | done | ✅ |
| 3 | Networking | 12–18 | — | done | ✅ |
| 4 | Python | 15–20 | — | done | ✅ |
| 5 | Linux Admin 2 / OOP | 15–20 | — | done | ✅ |
| 6 | Docker | 15–20 | — | done | ✅ |
| 7 | Kubernetes | 15–25 | — | done | ✅ |
| 8 | Ansible | 10–15 | — | done | ✅ |
| 9 | [AWS](stages/09-aws) | playlist ✅ 23 Nov · labs | Sat 28 Nov 2026 (moved from Thu 26) | | 🔄 Labs |
| 10 | [Git / GitHub](stages/10-git) | 4–6 | ~ early Dec 2026 | | ⏳ |
| 11 | [Terraform](stages/11-terraform) | 10–14 | ~ late Dec 2026 | | ⏳ |
| 12 | [CI/CD — Jenkins + GitHub Actions](stages/12-cicd) | 12–18 | ~ mid Jan 2027 | | ⏳ |
| 13 | [Observability — Prometheus, Grafana, logs, alerts](stages/13-observability) | 10–14 | ~ early Feb 2027 | | ⏳ |
| 14 | [Capstone project](stages/14-capstone) | 15–25 | ~ early Mar 2027 | | ⏳ |

**How each stage works:** about 1 hour of study a day (15 minutes minimum), then a 2–3 day lab sprint. Each stage has `tasks.md` (Basic → Intermediate → Advanced), `notes.md`, and `solutions/` holding code, configs and screenshots.

## Certifications (after the roadmap)

| Order | Certification | Est. prep | Exam fee (list) | Status |
|---|---|---|---|---|
| 1 | HashiCorp Terraform Associate (004) | 2–3 weeks | $70.50 | ⏳ |
| 2 | Certified Kubernetes Administrator (CKA) | 5–6 weeks | $445 (incl. 1 retake) | ⏳ |
| 3 | AWS Solutions Architect – Associate (SAA-C03) | 5–6 weeks (+1–2 wk AWS refresher) | $150 | ⏳ |
| 4 | AWS DevOps Engineer – Professional (DOP-C02) | 8–10 weeks | $300 | ⏳ |
| opt | Microsoft Agentic DevOps Engineer Expert (AZ-401) — replaces AZ-400 | later | — | — |
| opt | Prometheus Certified Associate (SRE path) / CKAD or CNPE (Platform path) | later | — | — |

Details and reasoning: [certifications/README.md](certifications/README.md)

## Past labs

Docker, Ansible and Kubernetes labs completed before this repo existed are being uploaded and improved in [past-labs/](past-labs). The fix list is in that folder's README.

## Repo layout

```
README.md          roadmap, certifications, progress table
progress-log.md    one line per day
stages/NN-name/    tasks.md · notes.md · solutions/
past-labs/         earlier labs + improvements
certifications/    plan, study resources, exam dates
```
