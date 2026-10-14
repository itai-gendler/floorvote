---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "notification",
      "effect": "changes",
      "to": "Read"
    }
  ],
  "permits": [
    {
      "related": [
        {
          "verb": "receives",
          "entity": "member-account"
        },
        {
          "verb": "holds",
          "entity": "standard-member"
        }
      ]
    },
    {
      "related": [
        {
          "verb": "receives",
          "entity": "member-account"
        },
        {
          "verb": "holds",
          "entity": "admin"
        }
      ]
    },
    {
      "related": [
        {
          "verb": "receives",
          "entity": "member-account"
        },
        {
          "verb": "holds",
          "entity": "owner"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/lib/notifications.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/routes/notificationsApi.ts"
    }
  ]
}
---

# Members mark only their own notifications read

Opening the panel or a bill marks the member's own notifications read and nobody else's.
