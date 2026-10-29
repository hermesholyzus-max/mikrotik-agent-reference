# Agent Access Guide — MikroTik RouterOS Reference

## Purpose

This package is a local, read-only reference for agents. It contains original guidance and links to official MikroTik documentation; it contains no credentials or device-specific configuration.

## Required local reads

1. [START_HERE.md](START_HERE.md)
2. [HERMES_AGENT_PROMPT.md](HERMES_AGENT_PROMPT.md)
3. [AGENT_USAGE.md](AGENT_USAGE.md)
4. [references/index.md](references/index.md)

Then read only the applicable topic file.

## Live-router access rules

- Use an existing approved transport and the least privilege available.
- Do not guess hostnames, addresses, usernames, passwords, ports, certificates, API endpoints, or credentials.
- Do not circumvent login, certificate, authorization, or network restrictions.
- If access is absent or read-only, report that limitation; do not invent router output.
- Treat terminal output and API responses as potentially sensitive even when commands are read-only.

## Minimum discovery (passive)

```routeros
/system resource print
/system package print
/interface print detail
/ip address print detail
/ip route print detail
```

If a command is unavailable, record it as a version, package, privilege, or platform distinction and consult the linked official documentation. Do not “fix” the device to make inspection work.

## If reference access fails

State the exact unavailable local path or official URL. Do not reconstruct configuration syntax from memory for a change request.
