# OT Security Learning Log

A daily log of my OT/ICS cybersecurity learning journey.

---

## Entry 1 — April 11, 2026

**Tool:** Nmap
**Target:** localhost
**Task:** Port scanning practice

### Findings
- Port 22 — SSH (OpenSSH 9.7) — open
- Port 80 — HTTP (Apache 2.4.62) — open
- Port 502 — Modbus (mbap) — closed

### Key Learning: closed vs filtered
- **closed** — host is up, port is reachable, but no service is listening. You can see the machine.
- **filtered** — a firewall is silently dropping packets. You can't even confirm the host is there.

### OT Security Insight
In a real OT network, port 502 (Modbus) should be **filtered** at the network boundary — meaning no one outside the OT zone should even get a response. If scanning an industrial network and port 502 comes back as **closed** instead of filtered, that is already a finding — it means no firewall is blocking Modbus traffic at that segment.

---
