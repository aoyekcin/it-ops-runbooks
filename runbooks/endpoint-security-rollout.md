# Runbook: Endpoint Security (EDR) Agent Rollout Across Sites

Rolling out or upgrading a security agent on hundreds of store, office and warehouse devices without disrupting sales.

| | |
|---|---|
| **Owners** | IT operations (rollout) together with Information Security (policy and approval) |
| **Change type** | Normal change, approved through the change process |

## 1. Prepare

- [ ] Agree the target version and policy with Information Security
- [ ] Build an inventory of target devices per site and device type (POS, back-office PC, kiosk, server)
- [ ] Confirm exclusions needed for POS / payment software so the agent does not block it
- [ ] Define success criteria: agent installed, reporting to the console, policy applied, no sales impact
- [ ] Prepare a rollback package and procedure

## 2. Pilot

- [ ] Choose a small pilot group: a few stores of different sizes plus some office devices
- [ ] Deploy outside opening hours
- [ ] Next business day: check sales, application performance, CPU and memory on POS devices
- [ ] Collect store feedback before widening the rollout

## 3. Phased rollout

| Wave | Scope | Go / no-go check before the next wave |
|---|---|---|
| 1 | Pilot sites | No sales impact for 2 business days |
| 2 | ~10% of sites | Agent reporting rate above target; no open incidents caused by the agent |
| 3 | ~50% of sites | Same checks |
| 4 | Remaining sites | Same checks |

## 4. Track

- Daily report: devices targeted vs installed vs reporting, per site
- Follow up on devices that are offline or failed to install
- Keep a short FAQ for the service desk so stores get consistent answers

## 5. Close

- [ ] Coverage target reached and confirmed in the security console
- [ ] Remaining exceptions documented with an owner and due date
- [ ] Lessons learned added to this runbook
