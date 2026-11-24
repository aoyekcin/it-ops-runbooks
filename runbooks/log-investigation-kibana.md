# Runbook: Log Investigation with Kibana

A structured approach to go from "there are errors" to "this is the cause and this team owns it".

## 1. Set the frame

- **Time range:** start a little before the first alert and end after it. The minutes before the errors often show the cause.
- **Index / data view:** pick the service or application logs you need.
- **Time zone:** check that Kibana's time zone matches the alert and ticket times.

## 2. Narrow down step by step

Start broad, then add one filter at a time and watch how the count changes.

```text
# 1. All errors for the service
service.name : "payment-api" and log.level : "error"

# 2. Group by error code or message to see the top patterns
#    (use a visualization or the field list "top values")

# 3. Focus on one pattern
service.name : "payment-api" and error.code : "TIMEOUT"

# 4. Follow one request across services using its ID
trace.id : "<trace-id>" or request.id : "<request-id>"
```

> Field names differ between environments. Check the field list in your data view and adjust the queries.

## 3. Questions to answer

| Question | Why it matters |
|---|---|
| When did the first error appear? | Correlate with deployments, config changes, provider incidents |
| Is it one error type or many? | One type usually means one cause |
| Is it one host / pod / region, or all? | Points to infrastructure vs application |
| Is it one customer, merchant or provider? | Points to configuration or an external party |
| Is it new, or recurring? | Recurring patterns belong in problem management |

## 4. Spot recurring alert patterns

- Save useful searches with clear names so the next person can reuse them.
- Compare the last 7 or 30 days: errors that appear every day at the same time often point to batch jobs, certificate checks or scheduled tasks.
- Turn every recurring pattern into either an automated fix, an alert tuning change, or a problem record.

## 5. Share the findings

Write a short summary for the receiving team:

```text
Since <time, TZ> we see <n> "<error>" errors in <service>,
only for <dimension, e.g. provider X / host Y>.
First occurrence: <time>. Sample request IDs: <id1>, <id2>, <id3>.
Saved search: <link>. Suspected area: <area>. Requested action: <action>.
```
