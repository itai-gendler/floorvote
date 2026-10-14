---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/routes/calendarApi.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/lib/calendarImport.ts"
    }
  ]
}
---

# Custom event

An event the team adds to its own calendar, such as a coalition call, optionally linked to bills.

## Information kept

- **Title** — what the event is
- **Date** — the day it takes place
- **Time** — the time, when set
- **Location** — where it takes place
- **Details** — notes about the event
- **Link** — a web address for the event
- **Bills** — the bills the event is about

## States

### Confirmed

The event is on the calendar.

### Cancelled

An admin cancelled the event; it can be restored.
