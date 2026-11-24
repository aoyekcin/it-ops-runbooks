# Post-Incident Review (Postmortem) Template

> Blameless: describe what happened and why the system allowed it, not who made a mistake.

## Summary

| | |
|---|---|
| **Incident ID** | <ID> |
| **Severity** | <SEV1–SEV4> |
| **Date** | <date> |
| **Duration** | <start> – <end> (<hh:mm>), time zone <TZ> |
| **Incident owner** | <name / team> |
| **Status of actions** | <open / in progress / done> |

**What happened (2–3 sentences):** <plain-language summary>

## Impact

- Who and what was affected: <users, stores, merchants, transactions>
- Size: <number or percentage>
- Business effect: <e.g. lost or delayed sales, SLA breach, customer complaints>

## Timeline

| Time (TZ) | Event |
|---|---|
| <hh:mm> | First signal (alert / customer call) |
| <hh:mm> | Incident declared, severity <n> |
| <hh:mm> | Escalated to <team> |
| <hh:mm> | Cause identified |
| <hh:mm> | Mitigation applied |
| <hh:mm> | Service restored, monitoring |
| <hh:mm> | Incident closed |

## Detection

- How was it detected? <monitoring / customer / staff>
- Could we have detected it earlier? How?

## Root cause

<Describe the technical cause and the contributing factors. Use "5 whys" if helpful.>

## What went well

- <…>

## What could be improved

- <…>

## Action items

| # | Action | Type (prevent / detect / respond) | Owner | Due date | Status |
|---|---|---|---|---|---|
| 1 | <…> | <…> | <…> | <…> | <…> |
