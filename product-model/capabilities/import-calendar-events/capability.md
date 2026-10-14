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
      "target": "api/src/lib/calendarImport.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/components/calendar/ImportEvents.tsx"
    }
  ]
}
---

# Import calendar events

An admin imports a spreadsheet or an .ics file of events into the calendar as custom events. Importing the same file again updates what changed instead of duplicating it.
