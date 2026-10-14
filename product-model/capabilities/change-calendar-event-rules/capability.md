---
{
  "availability": [
    {
      "place": "instance-web::settings"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/routes/eventRulesAdmin.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/lib/eventRules.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "shared/eventRules.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/pages/admin/EventRules.tsx"
    }
  ]
}
---

# Change calendar event rules

An admin chooses which events from the legislature's own calendar the instance shows: by committee, optionally narrowed to a kind of event, by kind or event type, by topic keywords matched against the title and agenda, or by bills the instance tracks on the agenda. Offered only while a covered state's data includes the legislature's calendar.
