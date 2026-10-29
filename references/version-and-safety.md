# Version, Preflight, and Rollback

## Identify before acting

```routeros
/system resource print
/system package print
/system routerboard print
/system identity print
```

Capture only the facts needed: RouterOS version, architecture/model, installed packages, and identity confirmation. `/system routerboard print` is platform-dependent; its absence is information, not an error to remediate.

## v6 / v7 boundary

- **Do not treat v6 and v7 as syntax-compatible.** Routing architecture, routing filters, policy-routing constructs, package layout, APIs, and feature availability can differ.
- For v7 route-policy work, use the official route/filter documentation for the installed release. In particular, v7 routing-filter AS-path matching semantics differ from v6; direct copy/paste can create incorrect policy.
- Do not infer that a late v7 feature exists on early v7 or v6. Inspect live menus/packages and verify the relevant official release documentation first.

## Passive configuration review

`export` without `file=` prints to the session rather than writing a router file, but output can disclose topology and comments. Prefer narrow menus and redact output. Never use `show-sensitive`.

```routeros
/interface export
/ip address export
/ip route export
/ip firewall filter export
```

Do not issue imports, resets, backups, exports with `file=`, package upgrades, or reboots without explicit approval.

## Approved-change rollback pattern

1. Confirm an out-of-band/local-console recovery method for management-path changes.
2. Record relevant current state in the work record without secrets.
3. Explain exact impact and rollback command/object state.
4. Make one small change, ideally in interactive Safe Mode where appropriate.
5. Read the changed object back and verify management and intended traffic behavior.
6. Exit Safe Mode only after explicit verification; otherwise undo and investigate.

MikroTik documents Safe Mode as an interactive CLI/Winbox protection whose changes can roll back after abnormal session termination. It is limited by session/history behavior and should not replace a recovery plan.

## Official sources

- [Configuration Management — Safe Mode and export behavior](https://help.mikrotik.com/docs/spaces/ROS/pages/328155/Configuration%2BManagement)
- [Backup — binary backups and sensitivity](https://help.mikrotik.com/docs/spaces/ROS/pages/40992852/Backup)
- [Current RouterOS documentation portal](https://manual.mikrotik.com/docs/introduction/)
