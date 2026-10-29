---
name: mikrotik-agent-reference
description: "Use when inspecting, planning, or safely changing MikroTik RouterOS v6/v7."
version: 1.0.0
author: Hermes Agent
license: Internal reference
metadata:
  hermes:
    tags: [mikrotik, routeros, networking, routing, firewall, vpn, safety]
---

# MikroTik RouterOS Agent Reference

Use this skill for RouterOS v6/v7 inspection, planning, verification, and approved minimal changes.

## Retrieval rule

Read `references/index.md`, then only the focused topic required. Follow the official links in that topic for command syntax and release-specific behavior. Do not load a complete manual or rely on an example from a different RouterOS major version.

## Scope

- Model-neutral and credential-free.
- RouterOS v6 and v7 distinctions are explicit where operationally material.
- Live device state is authoritative after version, model/architecture, package set, and privileges are confirmed.

## Safety

Default to passive, read-only inspection. Before an approved state-changing operation, establish a rollback and recovery path, make the smallest change, read the exact object back, and verify management access plus the intended data-plane behavior. Do not use `export show-sensitive`, publish device output without redaction, or assume a v7 feature/syntax exists on v6 or an older v7 release.

## Topic routing

- Version, rollback, preflight: `references/version-and-safety.md`
- Interfaces, bridge, VLAN, LAN inventory: `references/interfaces-and-lan.md`
- Routes and routing-policy differences: `references/routing.md`
- Firewall, NAT, VPN inventory: `references/firewall-and-vpn.md`
- Logs and non-invasive diagnostics: `references/diagnostics.md`

Official source links and a source-validation record are in `references/index.md`.
