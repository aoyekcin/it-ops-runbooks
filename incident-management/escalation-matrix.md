# Escalation Matrix

A clear escalation path removes hesitation during incidents. Use **functional escalation** (to the team that can fix it) and **hierarchical escalation** (to management, for decisions and communication) in parallel when the severity requires it.

## Support tiers

| Tier | Who | Scope | Escalate when |
|---|---|---|---|
| **Tier 1** | Service desk / platform support | Intake, triage, known fixes from runbooks, first communication | No runbook fix within the time box, or severity is SEV1/SEV2 |
| **Tier 2** | Operations / application support | Deeper troubleshooting, log analysis, configuration changes | Code change, infrastructure change or vendor action needed |
| **Tier 3** | Engineering, infrastructure, network, security teams | Code fixes, infrastructure and architecture changes | — |
| **External** | Vendors, banks, payment service providers, ISPs | Issues in third-party systems | Evidence points outside our systems |

## Time boxes before functional escalation

| Severity | Tier 1 time box | Tier 2 time box |
|---|---|---|
| SEV1 | Escalate immediately, keep working in parallel | 15 min |
| SEV2 | 15 min | 30 min |
| SEV3 | 2 h | 1 business day |
| SEV4 | Per queue | Per queue |

## Hierarchical escalation

| Severity | Notify |
|---|---|
| SEV1 | On-call lead + operations manager immediately; leadership if not mitigated within 1 h |
| SEV2 | On-call lead; operations manager if not mitigated within 2 h |
| SEV3–SEV4 | No management escalation unless the ticket breaches its SLA |

## What every escalation must contain

Use this checklist so the next team can start immediately:

- [ ] Incident ID and current severity
- [ ] Impact: who / how many / since when
- [ ] What has been checked and ruled out
- [ ] Evidence: dashboard links, log queries, error samples, timestamps (with time zone)
- [ ] What you need from the receiving team
- [ ] Who stays as incident owner

## Escalating to an external party (bank, PSP, vendor)

1. Confirm with data that the failure is on their side (e.g. errors only for one acquirer or provider).
2. Open a ticket through the agreed channel and record the reference number.
3. Send sample transaction IDs or request IDs, timestamps and error codes — never full card data.
4. Agree on an update interval and follow up on it.
5. Keep internal stakeholders informed of the external ticket status.
