---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "comment",
      "effect": "removes"
    }
  ],
  "permits": [
    {
      "related": [
        {
          "verb": "writes",
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
          "verb": "writes",
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
          "verb": "writes",
          "entity": "member-account"
        },
        {
          "verb": "holds",
          "entity": "owner"
        }
      ]
    },
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
      "target": "api/src/routes/commentsApi.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/routes/adminApi.ts"
    }
  ]
}
---

# Members delete their own comments; admins and owners delete any

A standard member deleting someone else's comment is refused.
