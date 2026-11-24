# Runbook: Store POS / Cash Register Offline

| | |
|---|---|
| **Trigger** | Store reports that one or more registers cannot complete sales |
| **Default severity** | SEV3 for one register with spares available; SEV2 if the whole store cannot sell; SEV1 if many stores are affected |
| **Owner** | Tier 1 service desk → Tier 2 store operations |

## 1. Scope the impact (first 5 minutes)

- [ ] How many registers in the store are affected? Is any register still working?
- [ ] Is it all payment types, or only card payments?
- [ ] Are other stores reporting the same issue? Check the queue and monitoring. **Several stores = possible central issue → escalate immediately.**
- [ ] Exact error message or screen, with a photo if possible.

## 2. Give the store a workaround

- Move sales to a working register, or use the backup card terminal if available.
- If only card payments fail, confirm whether cash and other payment methods still work.

## 3. Triage

| Check | How | If failing |
|---|---|---|
| Power and cables | Store staff checks power, network cable, peripherals | Reseat cables, power-cycle the device |
| Network | Ping or remote-connect to the register | Go to [Store network outage](store-network-outage.md) |
| POS application | Remote session: is the application running, any error dialog? | Restart the POS application, then the register |
| Peripherals | Receipt printer, scanner, card terminal connected and recognised? | Reconnect, restart the peripheral service |
| Card terminal | Terminal status, last successful transaction | Restart the terminal; check terminal parameters |
| Recent changes | Was there an update or deployment last night? | Check the change calendar; consider rollback via change process |

## 4. Escalate when

- The fix is not found within the time box for the severity (see [escalation matrix](../incident-management/escalation-matrix.md)).
- The same symptom appears in more than one store.
- A hardware replacement or on-site visit is needed.

## 5. Close

- [ ] Store confirms sales are working on all registers
- [ ] Ticket updated with root cause category (hardware / network / application / peripheral / user)
- [ ] If this is a repeat issue, link it to a problem record
