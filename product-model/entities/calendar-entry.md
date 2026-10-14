---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/queue/processor.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "shared/calendarKinds.ts"
    }
  ]
}
---

# Bill calendar entry

A date on a bill's legislative calendar, kept current from the legislature's data: a hearing, a markup, a meeting or a deadline.

## Information kept

- **Kind** — Hearing, Markup, Meeting or Deadline
- **Date** — the day it takes place
- **Time** — the time, when published
- **Location** — where it takes place
- **Description** — what the legislature calls it
- **Covered by** — the legislature event shown in its place, when one covers it

## States

### Confirmed

The entry is on the legislature's calendar.

### Cancelled

The legislature no longer lists the entry; calendars show it cancelled for two days.
