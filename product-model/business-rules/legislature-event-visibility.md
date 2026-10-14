---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "legislature-event",
      "effect": "changes",
      "facts": [
        "Shown"
      ]
    }
  ],
  "permits": [
    {
      "actors": [
        "admin",
        "owner"
      ]
    },
    {
      "unattended": true
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/lib/eventRules.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/routes/eventRulesAdmin.ts"
    }
  ]
}
---

# Admins, owners and the hourly sync decide which legislature events show

Which legislature events show changes only when an admin or owner saves calendar event rules, or when the hourly sync applies the saved rules to new events.
