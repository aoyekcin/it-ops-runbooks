# Example Postmortem: Card Payments Failing at Opening Time

> **Fictional example.** It is built from a common retail scenario to show how the [template](postmortem-template.md) is used. Names, numbers and times are illustrative.

## Summary

| | |
|---|---|
| **Severity** | SEV2 |
| **Duration** | 09:05 – 10:20 (1 h 15 min), local time |
| **Impact** | Card payments failed on registers in ~40 stores; cash payments worked |

**What happened:** An overnight update to the payment terminal configuration was rolled out to all stores in a single wave. On terminals with an older firmware version, the new configuration prevented the terminal from connecting to the payment host. Stores opening in the morning could not take card payments until the previous configuration was restored.

## Impact

- ~40 stores, card payments only, during the first hour of trading
- Customers were asked to pay in cash or wait; some sales were lost
- High call volume to the service desk between 09:05 and 09:45

## Timeline (local time)

| Time | Event |
|---|---|
| 02:00 | Terminal configuration update deployed to all stores |
| 09:05 | First store calls: "card payment declined with connection error" |
| 09:15 | Third store with the same symptom → incident declared SEV2 |
| 09:25 | Pattern found: all affected terminals run the older firmware |
| 09:35 | Payment team and vendor engaged; rollback decided |
| 09:50 | Previous configuration re-deployed to affected terminals |
| 10:20 | All affected stores confirm card payments work; incident resolved |

## Detection

Detected by store calls, not by monitoring. A synthetic check or an alert on terminal connection failures per store would have shown the problem before opening time.

## Root cause

The configuration was tested only on terminals with the current firmware. The inventory did not show that part of the estate still ran an older version, and the rollout went to all stores at once instead of in waves.

## What went well

- The service desk recognised a multi-store pattern quickly and escalated within 10 minutes
- The rollback procedure existed and worked

## What could be improved

- No pilot wave: the change reached every store at once
- The test plan did not cover all firmware versions in use
- Monitoring did not cover terminal-to-host connectivity

## Action items

| # | Action | Type | Owner | Status |
|---|---|---|---|---|
| 1 | Add firmware version to the terminal inventory report | Prevent | IT operations | Done |
| 2 | Require a pilot wave for all terminal configuration changes | Prevent | Change manager | Done |
| 3 | Test configuration changes on every firmware version in use | Prevent | Payment team | In progress |
| 4 | Alert on terminal connection failures per store before opening hours | Detect | Monitoring team | In progress |
