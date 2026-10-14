---
{
  "actors": [
    "standard-member",
    "admin",
    "owner"
  ],
  "access": "authenticated",
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/App.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/components/Sidebar.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/middleware/auth.ts"
    }
  ]
}
---

# Workspace

Where signed-in members follow the team's bills: the feed, the Bills page and each bill's page, the calendar, their notifications and their own account. Admins act here too, on priorities, positions, triage, custom field values, saved views and custom events.
