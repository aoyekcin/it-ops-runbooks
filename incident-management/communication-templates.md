# Incident Communication Templates

Short, factual and on a fixed rhythm. Avoid guessing at causes in early updates.

## 1. Initial notification

> **[SEV<n>] <Short title> — Investigating**
>
> **Impact:** <who is affected, e.g. "card payments failing for some merchants">
> **Started:** <time, time zone>
> **Status:** We are investigating. Workaround: <workaround or "none yet">.
> **Next update:** <time>
> **Incident owner:** <name / team>

## 2. Progress update

> **[SEV<n>] <Short title> — Update <#>**
>
> **Current status:** <Investigating / Identified / Mitigating / Monitoring>
> **What we know:** <one or two facts>
> **What we are doing:** <current action and owner>
> **Impact change:** <unchanged / reduced / increased>
> **Next update:** <time>

## 3. Mitigated / resolved

> **[SEV<n>] <Short title> — Resolved**
>
> **Resolved at:** <time, time zone> (duration: <hh:mm>)
> **Summary:** <what happened, in one or two sentences>
> **Customer action needed:** <none / description>
> **Follow-up:** A post-incident review will be shared by <date>.

## 4. Message to stores / end users (non-technical)

> We are aware that <service> is currently not working as expected. Our teams are working on it.
> Until it is fixed, please <workaround, e.g. "use register 2" or "accept card payments on the backup terminal">.
> We will update you again at <time>.

## Rules

- State facts, not assumptions. "We see errors from one provider" — not "the provider is down".
- Always give the time of the next update, and keep that promise even if there is no news.
- Use one channel as the source of truth; link to it from everywhere else.
- Times include the time zone.
