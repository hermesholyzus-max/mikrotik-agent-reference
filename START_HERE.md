# START HERE — MikroTik RouterOS Agent Reference

Use this package for **planning, inspection, and cautious RouterOS work**. It is a model-neutral reference; it is not a device configuration or an authorization to change a router.

## Reading order

1. Read [HERMES_AGENT_PROMPT.md](HERMES_AGENT_PROMPT.md).
2. Read [AGENT_USAGE.md](AGENT_USAGE.md).
3. Read [references/index.md](references/index.md).
4. Open only the focused topic file needed for the task.
5. Inspect live state before proposing commands; do not assume RouterOS major version, hardware, topology, privileges, or transport.

## Hard safety boundary

- Default to **read-only terminal/API inspection**.
- Do not change configuration, create router files, upgrade, reset, reboot, enable services, or send test traffic unless the user explicitly authorizes that action.
- Never expose or request passwords, API tokens, private keys, PSKs, backup files, or `export show-sensitive` output.
- For an approved change, establish a rollback path first and use one small, verified change at a time.

## Version boundary

This package covers **RouterOS v6 and v7** at a high level. Commands and feature availability differ. Read [references/version-and-safety.md](references/version-and-safety.md) before using a command that is not purely observational.

## Official documentation

- Current documentation portal: <https://manual.mikrotik.com/docs/introduction/>
- Official RouterOS documentation archive: <https://help.mikrotik.com/docs/spaces/ROS/overview>

If official documentation or live read access is unavailable, say so and avoid fabricating syntax.