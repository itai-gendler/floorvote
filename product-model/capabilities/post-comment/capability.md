---
{
  "availability": [
    {
      "place": "instance-web::workspace"
    }
  ],
  "domain": "bills",
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/routes/billsApi/engagementRoutes.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/lib/mentions.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/lib/replies.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/lib/notifications.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/lib/sanitizeHtml.ts"
    }
  ]
}
---

# Post comment

A member comments on a bill, optionally @-mentioning members, roles, or — for admins — everyone. Mentioned people get a mention; everyone else who has commented on the bill gets a reply notification. Both are emailed unless the instance turned conversation emails off.
