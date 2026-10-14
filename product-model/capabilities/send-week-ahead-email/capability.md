---
{
  "availability": [
    {
      "place": "instance-web::workspace"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/lib/weekAhead.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/lib/weekAheadEmail.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/index.ts"
    }
  ]
}
---

# Send week-ahead email

When the instance has the week-ahead email on, it emails members on the chosen weekday a preview of the next seven days grouped by day: custom events, hearings of prioritized bills, and legislature events with a prioritized bill on the agenda or selected by the calendar event rules.
