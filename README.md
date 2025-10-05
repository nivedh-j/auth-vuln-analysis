# auth-vuln-analysis

**Course project / lab report** — analysis of web authentication behavior performed as an authorized TryHackMe exercise.  
> Note: This repository contains a public writeup, screenshots, and analysis. All offensive scripts and Burp project files are kept private and are **not** published here.

## Summary
This repository documents my TryHackMe lab exercise focused on web authentication testing using Burp Suite. The goal was to explore authentication weaknesses and rate-limiting behaviors in a controlled lab environment, and to produce recommendations for defensive mitigation.

## What’s in this repo (public)
- `README.md` — project overview and responsible use statement.
- `writeup/` — step‑by‑step analysis, methodology, and findings (redacted).
- `screenshots/` — non-sensitive screenshots showing Burp interface and lab results.
- `notes/` — high-level notes, test environment description, and remediation suggestions.
- `SECURITY.md` — how to responsibly disclose issues found (if applicable).

> **Private files (not included here)**: Burp Suite project files, working brute‑force scripts, exported wordlists, and any files containing credentials or live request/response data. These are stored in a private repository or local secure storage.

## Responsible use / ethics
All testing was performed on TryHackMe lab systems to which I had explicit authorization. This work is for educational and defensive purposes only. Do NOT use any techniques, tools, or code from this repository against systems or networks for which you do not have explicit permission.

## Key findings (summary)
- Authentication endpoint `/login` exhibited weak rate limiting under simulated conditions.
- Account lockout was not enforced after repeated failed attempts (lab conditions).
- Recommended mitigations:
  - Implement exponential backoff + IP rate limiting
  - Add account lockout / progressive delay measures
  - Introduce monitoring/alerting for repeated failed logins

## How to reproduce (public guidance)
This public repo does **not** contain exploit code. To reproduce similar tests on your own authorized lab:
1. Use an isolated VM or lab platform (TryHackMe/OWASP Juice Shop).
2. Configure Burp Suite as proxy and use Intruder/Repeater with synthetic test accounts.
3. Respect rate limits and run tests only against systems you control or have permission to test.

## Attribution & license
This repository documents lab work only. The public content is licensed for educational reuse with attribution. See `LICENSE` for details.

---

