# Runbook: Store / Branch Network Outage

| | |
|---|---|
| **Trigger** | Multiple devices in one site are unreachable, or monitoring shows the site down |
| **Default severity** | SEV2 for a single site that cannot trade; SEV1 if multiple sites are down |
| **Owner** | Tier 1 → network team / ISP |

## 1. Confirm and scope

- [ ] Is the whole site down, or only some devices (one switch, one VLAN, Wi-Fi only)?
- [ ] Is it one site or several? Several sites at once usually points to a central component (data centre, VPN concentrator, core service) or a shared ISP.
- [ ] When did monitoring last see the site as healthy?

## 2. Workaround for the site

- Switch to the backup connection (e.g. mobile/4G router) if the site has one.
- If card payments depend on the network, confirm the store's offline or backup payment procedure.

## 3. Triage

| Check | How | Notes |
|---|---|---|
| Power | Ask staff: router and switch lights on? | Power cuts are a common cause |
| Router / modem | Status lights, power-cycle if agreed | Record the time of the restart |
| Primary line | ISP status, line test from the ISP portal | Open an ISP ticket early; record the reference |
| VPN tunnel | Tunnel status on the central side | A tunnel can be down while the internet line is up |
| Switch | Ports up? Loop? | A cable loop can take down a whole site |
| DNS / DHCP | Clients receiving IP addresses? Name resolution working? | Typical symptom: "connected but nothing works" |

## 4. Escalate

- Network team: if the issue is in our equipment or configuration.
- ISP: if the line is down — send site ID, address, contact person and opening hours.
- On-site technician: if hardware needs replacing.

## 5. Close

- [ ] Monitoring shows the site healthy for at least one full check interval
- [ ] Store confirms all registers and back-office systems are working
- [ ] Backup connection switched back to standby if it was used
- [ ] Root cause recorded (power / ISP / hardware / configuration)
