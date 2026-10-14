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
      "target": "web/src/components/calendar/EventForm.tsx"
    }
  ]
}
---

# Add custom event

An admin adds an event of the team's own to the calendar, such as a coalition call, optionally linked to bills.
