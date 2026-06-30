# Bastinez Manor Network

Repo to help me monitor, harden and generally improve my home's LAN.

This is a working repository for documenting the home network, tracking security
hardening tasks, and storing the scripts and configs that keep everything healthy.

## Goals

- **Monitor** — know what's on the network and what it's doing.
- **Harden** — reduce attack surface and keep firmware/credentials in good shape.
- **Improve** — better segmentation, reliability, and automation over time.

## Suggested structure

As the project grows, content will live under directories like:

| Path          | Purpose                                                        |
| ------------- | -------------------------------------------------------------- |
| `docs/`       | Network topology, runbooks, decisions, notes                  |
| `inventory/`  | Device inventory, subnet/VLAN maps, DHCP reservations         |
| `scripts/`    | Discovery scans, backups, automation                          |
| `configs/`    | Sanitized exports of router/AP/switch configs                 |
| `monitoring/` | Monitoring stack config (Pi-hole, Prometheus/Grafana, etc.)   |

## Getting started

See [`TODO.md`](./TODO.md) for the phased checklist of work to do.

## ⚠️ Security note

This repo is public. **Never commit secrets** — no passwords, API keys, private
keys, WireGuard configs, or full public IP addresses. Sanitize any config
exports before adding them, and keep real credentials in a password manager.
