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
      "target": "web/src/components/calendar/SubscribeCalendar.tsx"
    }
  ]
}
---

# Subscribe to calendar

A member takes the calendar's subscription link to their own calendar app, which then follows the team calendar.
