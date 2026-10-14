---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "view-calendar"
    },
    {
      "type": "capability",
      "id": "read-calendar-feed"
    },
    {
      "type": "capability",
      "id": "send-week-ahead-email"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/lib/calendarVisibility.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/lib/weekAhead.ts"
    }
  ]
}
---

# A bill's calendar entries appear only while the bill has a priority

The calendar, its subscription and the week-ahead email show a bill's hearings, markups, meetings and deadlines only while the bill has a priority, so a large keyword match does not flood the calendar. An entry covered by a legislature event the instance shows appears as that event instead; a deadline is never covered.

## Rationale

Instances often track hundreds of keyword matches; the calendar is meant for the bills the team decided to act on.
