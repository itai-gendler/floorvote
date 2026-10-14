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
      "target": "api/src/lib/bodyEvents.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/lib/eventRules.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "central/src/cron/body-events.ts"
    }
  ]
}
---

# Update legislature events

Every hour, for covered states whose data includes the legislature's own calendar, the instance brings in the legislature's events and decides with its calendar event rules which ones it shows.
