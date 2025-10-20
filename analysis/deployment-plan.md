# Deployment Plan — Cowrie Honeypot

## 1) Infrastructure
- Virtualization: (VirtualBox / VMware / Proxmox / Cloud VPS — to choose)
- Guest OS: Debian 12 minimal
- Resources: 2 vCPU / 4 GB RAM / 20 GB disk
- Dedicated VM only for the honeypot

## 2) Network & Security
- The honeypot will NOT run on a home LAN
- It will be placed in an isolated network segment or behind a firewall rule set
- Outbound traffic will be blocked by default (egress deny)
- Only the logging endpoint will be allowed outbound (`<IP>:<PORT>` to define later)
- Inbound allowed only on the SSH emulation port (default Cowrie: 2222)

## 3) Software Stack (initial scope)
- Cowrie (SSH/Telnet honeypot)
- UFW firewall for egress control
- Log retention locally (/opt/cowrie/logs), redacted extracts published in repo

## 4) Deployment Conditions / Rules of Engagement
- No real execution of attacker payloads (Cowrie emulation only)
- No outbound traffic to the public internet except collector
- Logs will be anonymized before publication
- This environment is for **observation and documentation only**, not retaliation
