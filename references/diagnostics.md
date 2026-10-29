# Diagnostics and API Safety

## Passive diagnostics first

```routeros
/log print without-paging
/interface print stats-detail
/ip firewall connection print detail
/ip arp print detail
/ip neighbor print detail
/ip route print detail
```

Narrow filters before collecting broad output. Logs, connection tables, neighbor information, route comments, interface descriptions, and API responses can be sensitive operational data.

## Tests that are not passive

Keep these outside the default read-only phase because they generate traffic, alter counters, consume resources, or may expose data: `ping`, `traceroute`, `tool bandwidth-test`, `fetch`, `sniffer`, and active packet generation. Use them only with explicit scope/approval, rate or count limits where applicable, and a statement of expected impact.

## API boundary

REST/API access can execute commands and mutate configuration. Restrict an agent to approved read-only calls and a least-privilege credential/transport; do not place credentials in shell history, prompts, tickets, or this reference. A `GET`/`print` request still requires authorization and can return sensitive data.

When invoking any API, explicitly request only needed properties and bound potentially long-running queries. Verify the endpoint/version capability in current official docs before use.

## Escalation evidence

A useful no-change report includes: time window; symptom; affected direction/path; relevant interface/route/rule identifiers; selected redacted log lines/counters; evidence gaps; and next safe observation. Do not claim causality from one counter or one router-originated probe.

## Official sources

- [REST API](https://help.mikrotik.com/docs/spaces/ROS/pages/47579162/REST%2BAPI)
- [Files — Router file handling](https://help.mikrotik.com/docs/spaces/ROS/pages/2555971/Files)
- [Current RouterOS documentation portal](https://manual.mikrotik.com/docs/introduction/)
