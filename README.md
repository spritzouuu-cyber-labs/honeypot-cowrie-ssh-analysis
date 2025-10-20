# Honeypot — Cowrie (SSH) Threat Observation & Analysis

**Goal**  
Deploy a safe, isolated SSH honeypot (Cowrie) to observe real-world attacks and document findings for recruiters.

**Status**  
Repository scaffolding done. VM & data collection coming next.

## Objectives
- Expose a realistic SSH surface (Cowrie) in a safe, isolated network.
- Collect attacker TTPs (bruteforce patterns, command sequences).
- Produce a concise analysis report with anonymized evidence.

## High-Level Architecture
Internet → Firewall → **Honeypot VM (Cowrie)** → (JSON logs/Filebeat) → **Collector/ELK**  
Egress from the honeypot is **blocked** except to the logging endpoint.

## Repository Layout
- `deploy/` – install & firewall scripts (to be added)
- `configs/` – example configs (no secrets)
- `logs_redacted/` – anonymized sample logs for the write-up
- `analysis/` – report & timeline (executive-friendly)
- `docs/` – public summary for recruiters
- `screenshots/` – architecture & dashboard images

## Safety & Legal
- Honeypot runs on an **isolated VLAN / network** (not on my home LAN).
- **Outgoing traffic is denied** except to the log collector.
- Evidence published here is **anonymized** (IPs/credentials redacted).
- Research/education only. No offensive use.
