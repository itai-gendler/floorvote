---
{
  "entities": [
    {
      "entity": "instance-settings",
      "shows": [
        "Calendar event rules"
      ],
      "collects": [
        "Calendar event rules"
      ]
    },
    {
      "entity": "legislature-event",
      "shows": [
        "Title",
        "Date",
        "Time",
        "Committee",
        "Kind",
        "Agenda",
        "Shown"
      ]
    }
  ],
  "entryPoints": [
    {
      "instance-web": "/admin/calendar-events"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/pages/admin/EventRules.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/routes/eventRulesAdmin.ts"
    }
  ]
}
---

# Calendar events

Which legislature events the instance shows, with a preview of the next 120 days of events. Offered only while a covered state's data includes the legislature's own calendar.
