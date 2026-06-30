# TODO — Bastinez Manor Network

A phased checklist for monitoring, hardening, and improving the home LAN.

## Phase 0 — Repo scaffolding
- [x] Add a `README.md` describing the project's purpose and structure
- [ ] Add `.gitignore` (ignore secrets, `.env`, scan outputs, `*.pcap`, etc.)
- [ ] Decide on a structure (`docs/`, `inventory/`, `scripts/`, `configs/`, `monitoring/`)
- [ ] Add a `SECURITY.md` / notes file — never commit real credentials, keys, or full public IPs

## Phase 1 — Inventory & baseline
*You can't secure what you can't see.*
- [ ] Document network topology (ISP → router/gateway → switches → APs → devices)
- [ ] Build a device inventory: hostname, MAC, IP, owner, purpose, OS/firmware
- [ ] Map subnets / VLANs and current DHCP ranges
- [ ] Record current firmware versions for router, APs, switches, IoT
- [ ] Run a baseline discovery scan (`nmap -sn 192.168.x.0/24`) and save the output

## Phase 2 — Monitoring
- [ ] Stand up a monitoring stack (Pi-hole/AdGuard for DNS, Prometheus + Grafana, or Uptime Kuma)
- [ ] Enable router/firewall logging and forward logs somewhere durable (syslog)
- [ ] Set up new-device-on-network alerts (Pi-hole, Fing, or arpwatch)
- [ ] Track bandwidth/traffic per device; flag anomalies
- [ ] Optional: passive IDS (Suricata/Zeek) on a mirror/SPAN port

## Phase 3 — Hardening
- [ ] Change default admin credentials on router/APs/IoT; store in a password manager
- [ ] Update firmware on all network gear; set a recurring update reminder
- [ ] Segment the network: separate VLAN/SSID for IoT and guests
- [ ] Lock down the gateway: disable WPS, UPnP (if not needed), remote admin, Telnet
- [ ] Enforce WPA3 (or WPA2-AES) with a strong passphrase
- [ ] Set up DNS filtering (Pi-hole/AdGuard/NextDNS)
- [ ] Review and minimize open ports / port forwards; verify with an external scan
- [ ] Consider a WireGuard VPN for remote access instead of exposed services

## Phase 4 — Automation & maintenance
- [ ] Script recurring scans (nmap diff against the inventory) via cron
- [ ] Schedule config/firmware backups of network gear
- [ ] Write a runbook: "what to do when an unknown device appears"
- [ ] Set a monthly review checklist (logs, updates, new devices)
