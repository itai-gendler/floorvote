---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "custom-event",
      "effect": "changes"
    }
  ],
  "permits": [
    {
      "actors": [
        "admin",
        "owner"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/routes/calendarApi.ts"
    }
  ]
}
---

# Only admins and owners change, cancel or restore custom events

Only custom events can be edited, cancelled or restored, and only by admins and owners; bill calendar entries and legislature events follow the legislature.
