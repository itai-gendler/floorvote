---
{
  "type": "api",
  "actors": [
    "calendar-app"
  ],
  "entryPoints": [
    {
      "api": "/api/calendar/feed/<calendar feed link>.ics"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/routes/calendarApi.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/lib/ical.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/lib/calendarIcsBody.ts"
    }
  ]
}
---

# Calendar feed

The instance's calendar as an iCalendar subscription at its secret link, which any calendar app can subscribe to. Each event keeps one identity for as long as it exists, so a changed or cancelled event updates in subscribers' calendars instead of appearing twice.
