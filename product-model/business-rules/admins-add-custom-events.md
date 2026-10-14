---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "custom-event",
      "effect": "creates"
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

# Only admins and owners add custom events

Adding or importing events to the team calendar is refused to standard members.
