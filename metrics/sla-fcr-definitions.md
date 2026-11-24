# Support Metrics: Definitions and How to Measure Them

Metrics only help if everyone calculates them the same way. These are the definitions used in this repository.

| Metric | Definition | Formula | Watch out for |
|---|---|---|---|
| **SLA compliance (response)** | Share of tickets first responded to within the target time for their priority | tickets responded in time ÷ all tickets | Count only business hours if the SLA is business hours |
| **SLA compliance (resolution)** | Share of tickets resolved within the target time | tickets resolved in time ÷ all resolved tickets | Define when the clock pauses (e.g. waiting for customer) |
| **FCR – First Contact Resolution** | Share of tickets solved during the first contact, without escalation or callback | tickets solved at first contact ÷ all eligible tickets | Exclude ticket types that can never be solved at first contact (e.g. hardware replacement) |
| **MTTA – Mean Time to Acknowledge** | Average time from alert/ticket creation to the first human acknowledgement | Σ(ack time − created time) ÷ count | Measure from the alert, not from when someone noticed the alert |
| **MTTR – Mean Time to Restore** | Average time from impact start to service restored | Σ(restored − impact start) ÷ incidents | Use impact start, not ticket creation, for incidents |
| **Reopen rate** | Share of tickets reopened after being closed | reopened ÷ closed | High values often mean closing too early |
| **Recurring ticket rate** | Share of tickets in categories that repeat often | tickets in top recurring categories ÷ all tickets | The best input for problem management |

## Using metrics to reduce ticket volume

1. Export one to three months of tickets with category, site and resolution notes.
2. Group by category and resolution; list the top 10 recurring issues.
3. For each recurring issue, choose one action:
   - **Fix it permanently** (problem record with an owner)
   - **Automate it** (self-service, script, monitoring alert)
   - **Document it** (runbook or user guide so Tier 1 or users can solve it)
4. Re-measure the same categories one month later.

This is the approach behind reducing recurring tickets and improving FCR: most volume comes from a small number of repeat issues, and each one needs either a fix, an automation or a clear guide.
