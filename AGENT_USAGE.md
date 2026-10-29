# Agent Usage — MikroTik RouterOS

## Scope

This concise, original reference routes an agent to official MikroTik documentation and safe inspection commands. It deliberately excludes device exports, credentials, topology data, and copied manual corpus.

## Start-of-task procedure

1. Record access method and privilege boundary; do not bypass it.
2. Identify model/architecture and RouterOS version from live state.
3. Read the relevant file in `references/` and its official links.
4. Collect only the live state relevant to the task.
5. State the intended outcome, dependencies, risk, rollback method, and verification before any change.

## Safe read-only baseline

Run only commands applicable to the observed major version and permissions:

```routeros
/system resource print
/system routerboard print
/system package print
/system identity print
/interface print detail
/ip address print detail
/ip route print detail
/ip dns print
/log print without-paging
```

These commands query state. Their output can still contain names, addresses, routes, comments, or operational details; minimize collection and redact before sharing. Do **not** append `file=` to exports or diagnostic commands unless a router-file write is explicitly approved.

## Topic routing

| Task | Read |
|---|---|
| Version, agent limits, rollback | `references/version-and-safety.md` |
| Interface, bridge, VLAN, address/DHCP inventory | `references/interfaces-and-lan.md` |
| Routes, policy routing, routing protocols | `references/routing.md` |
| Firewall/NAT/VPN observation | `references/firewall-and-vpn.md` |
| Logs, counters, packet/connection investigation | `references/diagnostics.md` |

## Change gate

A state-changing command needs explicit user approval after the agent has:

- confirmed device identity, RouterOS version, and current management path;
- identified affected objects and dependencies;
- confirmed an available rollback path and out-of-band recovery option for management-plane risk;
- presented the smallest change and an exact post-change read-back/test;
- separated configuration changes from traffic-generating tests.

Use Safe Mode only during an approved interactive CLI change and only when its behavior/limits are understood. It is not a substitute for a tested backup or console recovery plan.

## Completion report

Report: device/version observed; exact commands run; changes (or explicitly none); read-back evidence; tests performed; untested items; rollback status; official sources used. Never claim end-to-end forwarding merely because the router itself has an active route or can originate traffic.