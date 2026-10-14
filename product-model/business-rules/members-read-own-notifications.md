---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "notification",
      "effect": "reads"
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

# Members see only their own notifications

A member's notifications panel lists only notifications addressed to them.
