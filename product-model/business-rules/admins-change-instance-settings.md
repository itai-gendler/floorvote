---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "instance-settings",
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
      "target": "api/src/routes/adminApi.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/routes/calendarApi.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/routes/eventRulesAdmin.ts"
    }
  ]
}
---

# Only admins and owners change instance settings

Keywords, AI instructions, the new match threshold, labels, notification settings, sidebar widgets, calendar event rules and the calendar link are set by admins and owners. Covered states, demo mode, sign-in verification and legal terms are the operator's and change only with the deployment.
