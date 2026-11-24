# Incident Severity Matrix

Severity is decided by **business impact**, not by how technically interesting the issue is. When in doubt, pick the higher severity — downgrading later is cheap.

| Severity | Definition | Examples | Response target | Update rhythm | Resolution target |
|---|---|---|---|---|---|
| **SEV1 – Critical** | Core service down or severely degraded for many users or sites; direct revenue impact | Payment processing failing for all merchants; checkout down in many stores; error rate far above normal | 15 min | Every 30 min | 4 h |
| **SEV2 – High** | Major function degraded, workaround exists, or a single important site/customer fully down | One bank or payment provider failing; one large store offline; latency well above SLO | 30 min | Every 1 h | 8 h |
| **SEV3 – Medium** | Limited impact, small group of users, workaround available | One register down in a store with spares; a back-office report delayed | 4 h (business hours) | Daily | 3 business days |
| **SEV4 – Low** | Minor issue, cosmetic, or a request | Printer issue at one desk; access request; documentation fix | 1 business day | On change | Per queue SLA |

> The time values are examples. Align them with your own SLAs and customer contracts.

## Quick decision questions

1. Is money or a core customer journey (payment, checkout, login) blocked? → **SEV1 or SEV2**
2. How many users, stores or merchants are affected — one, some, or most?
3. Is there a working workaround right now?
4. Is the impact growing (error rate climbing, more stores calling)?
5. Is there a regulatory, security or contractual dimension? → raise one level

## Severity changes

- **Upgrade** immediately when impact grows; announce it in the incident channel.
- **Downgrade** only after impact is confirmed reduced for a full monitoring interval.
- Record every change and its reason in the incident ticket timeline.
