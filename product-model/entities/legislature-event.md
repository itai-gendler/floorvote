---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/lib/bodyEvents.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/lib/eventRules.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "shared/eventRules.ts"
    }
  ]
}
---

# Legislature event

An event on a legislature's own calendar, from a covered state whose data provider publishes one, such as a hearing, roundtable, markup or meeting, with or without bills on its agenda.

## Information kept

- **Title** — the event's title
- **Date** — the day it takes place
- **Time** — the time, when published
- **Location** — where it takes place
- **Committee** — the committee holding it, and any held jointly with it
- **Kind** — Hearing, Markup or Meeting, and the legislature's own event type
- **Agenda** — the topics and bills on its agenda
- **Shown** — whether the instance's calendar event rules select it

## States

### Confirmed

The legislature lists the event.

### Cancelled

The legislature cancelled the event.
