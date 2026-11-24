# IT Operations Runbooks

Practical runbooks, templates and process guides for **IT operations, platform support and incident management** — written from hands-on experience supporting payment platforms and multi-country retail IT (500+ stores).

> All scenarios, names, hosts and numbers in this repository are generic examples. No company, customer or production data is included.

## Why this repository exists

Most outages are not solved by heroics but by a calm, repeatable process: detect early, triage correctly, escalate to the right team, communicate clearly, and learn from every incident. This repository collects the checklists and templates I use to do exactly that.

## Contents

| Area | What's inside |
|---|---|
| [Incident management](incident-management/) | Severity matrix, escalation matrix, stakeholder communication templates |
| [Runbooks](runbooks/) | Step-by-step guides for common store, network, payment and endpoint issues |
| [Problem management](problem-management/) | Postmortem template and a worked example |
| [Change management](change-management/) | Change request template and a multi-site rollout checklist |
| [Metrics](metrics/) | How SLA, FCR, MTTA and MTTR are defined and measured |

### Runbooks

| Runbook | Typical trigger |
|---|---|
| [Store POS / cash register offline](runbooks/store-pos-offline.md) | Store reports that checkout is down |
| [Store network outage](runbooks/store-network-outage.md) | Multiple devices in one site lose connectivity |
| [Payment error rate spike](runbooks/payment-error-spike.md) | Monitoring alert on failed transactions or latency |
| [Log investigation with Kibana](runbooks/log-investigation-kibana.md) | Root cause needed for an error pattern |
| [Endpoint security agent rollout](runbooks/endpoint-security-rollout.md) | Deploying or upgrading an EDR agent across sites |

## Principles

1. **Restore service first, find the root cause second.** Workarounds are fine during an incident; permanent fixes go through problem management.
2. **Escalate on time, not on feeling.** Use the severity and escalation matrices; a late escalation costs more than an unnecessary one.
3. **Communicate on a fixed rhythm.** Stakeholders should never have to ask for an update.
4. **Write it down.** Every recurring ticket is a missing runbook or a missing fix.
5. **Blameless reviews.** Postmortems look for weak processes and systems, not people to blame.

## How to use

- Copy a template, fill in the placeholders in `<angle brackets>`, and store the result in your ticketing or wiki tool.
- Adapt thresholds (SLA times, alert levels) to your own environment — the values here are examples.

## Tools these runbooks assume

ITSM tool (e.g. Jira Service Management, ServiceNow) · Monitoring (e.g. Grafana) · Log search (e.g. Kibana / Elastic Stack) · Remote support tooling · Endpoint management and EDR tooling

## Author

**Aykut Öyekcin** — IT Operations & Platform Support Specialist
[LinkedIn](https://www.linkedin.com/in/aykutoyekcin) · [GitHub](https://github.com/aoyekcin)

## License

[MIT](LICENSE) — free to reuse and adapt.
