# Runbook: Payment Error Rate or Latency Spike

| | |
|---|---|
| **Trigger** | Monitoring alert: failed transaction rate, timeout rate or latency above threshold |
| **Default severity** | SEV1 if most transactions fail; SEV2 if one bank / PSP / merchant group is affected |
| **Owner** | Platform support (Tier 1/2) → engineering, infrastructure, external providers |

## 1. Validate the alert (first 5 minutes)

- [ ] Open the payment dashboard: error rate, success rate, latency (p50 / p95 / p99) and traffic volume.
- [ ] Is it a real spike, or low traffic making percentages look high?
- [ ] Compare with the same time yesterday or last week.

## 2. Find the blast radius

Break the errors down by dimension. The pattern usually points straight to the owner:

| Errors concentrated in… | Likely area | Escalate to |
|---|---|---|
| One acquiring bank or PSP | External provider | Provider support (with sample IDs) |
| One merchant or integration | Merchant configuration or integration | Integration / account team |
| One transaction type (e.g. 3-D Secure, refunds) | Specific flow or dependency | Owning engineering team |
| One service instance or region | Infrastructure | Infrastructure / SRE |
| Everything at once | Core platform, database, network, recent deployment | Engineering on-call + infrastructure |

## 3. Check what changed

- [ ] Deployments, configuration changes or certificate renewals in the last hours
- [ ] Provider maintenance announcements
- [ ] Traffic patterns (campaigns, unusual volume)

## 4. Collect evidence before escalating

- Dashboard screenshot or link with the time range
- Error codes and their counts
- 3–5 sample transaction or request IDs with timestamps
- The log query you used (see [log investigation](log-investigation-kibana.md))

> Never share full card numbers or other sensitive cardholder data in tickets, chats or emails.

## 5. Mitigate

Typical mitigations, decided together with the owning team:

- Route traffic away from a failing provider, if routing is available
- Roll back a recent deployment or configuration change through the change process
- Scale or restart an unhealthy component

## 6. Monitor and close

- [ ] Error rate and latency back to the normal band for at least one full interval
- [ ] Affected merchants or stakeholders informed
- [ ] Incident timeline completed; postmortem scheduled for SEV1/SEV2
