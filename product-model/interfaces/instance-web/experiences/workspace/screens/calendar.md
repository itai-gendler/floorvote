---
{
  "entities": [
    {
      "entity": "calendar-entry",
      "shows": [
        "Kind",
        "Date",
        "Time",
        "Location",
        "Description"
      ]
    },
    {
      "entity": "legislature-event",
      "shows": [
        "Title",
        "Date",
        "Time",
        "Location",
        "Committee",
        "Kind",
        "Agenda"
      ]
    },
    {
      "entity": "custom-event",
      "shows": [
        "Title",
        "Date",
        "Time",
        "Location",
        "Details",
        "Link",
        "Bills"
      ],
      "collects": [
        "Title",
        "Date",
        "Time",
        "Location",
        "Details",
        "Link",
        "Bills"
      ]
    },
    {
      "entity": "instance-settings",
      "shows": [
        "Calendar feed link"
      ]
    },
    {
      "entity": "bill",
      "shows": [
        "Bill number",
        "Title",
        "Priority"
      ]
    }
  ],
  "entryPoints": [
    {
      "instance-web": "/calendar"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/pages/Calendar.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/routes/calendarApi.ts"
    }
  ]
}
---

# Calendar

The team's shared calendar: hearings and deadlines of prioritized bills, the legislature events the instance shows, and the team's custom events, with the link to subscribe from a calendar app.
