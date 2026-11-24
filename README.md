# IT Operations Runbooks

Runbooks, templates and checklists for IT operations and incident management. They're based on how I've worked supporting 500+ retail stores in several countries and, more recently, payment platforms.

> Everything here is generic. Names, hosts and numbers are examples, not real company or customer data.

## Why

In my experience most incidents go well or badly depending on the basics: noticing early, picking the right severity, calling the right team on time and keeping people updated. I wanted those basics written down in one place instead of in my head.

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

## A few rules I follow

1. Get the service back first, find the root cause after. A workaround is fine during an incident; the real fix goes through problem management.
2. Escalate based on the matrix, not on a feeling. Escalating late usually costs more than escalating too early.
3. Send updates on a fixed schedule so nobody has to ask.
4. If the same ticket keeps coming back, there's a runbook or a fix missing.
5. Postmortems are blameless. Look at the process, not the person.

## How to use

Copy a template, fill in the `<placeholders>` and keep it in your ticketing tool or wiki. SLA times and alert thresholds are examples; change them to fit your environment.

## Tools assumed

An ITSM tool (Jira Service Management, ServiceNow), monitoring (Grafana), log search (Kibana / Elastic), remote support, endpoint management and EDR.

## Author

Aykut Öyekcin, IT Operations & Platform Support Specialist
[LinkedIn](https://www.linkedin.com/in/aykutoyekcin) · [GitHub](https://github.com/aoyekcin)

## License

[MIT](LICENSE). Feel free to reuse and adapt.
