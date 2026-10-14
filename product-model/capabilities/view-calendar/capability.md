---
{
  "availability": [
    {
      "place": "instance-web::workspace"
    }
  ],
  "domain": "calendar",
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/routes/calendarApi.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/lib/calendarVisibility.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/pages/Calendar.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/components/calendar/MonthGrid.tsx"
    }
  ]
}
---

# View calendar

A member opens the team's shared calendar: hearings, markups, meetings and deadlines of prioritized bills, the legislature events the instance shows, and the team's custom events.
