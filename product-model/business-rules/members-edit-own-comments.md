---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "comment",
      "effect": "changes",
      "facts": [
        "Content"
      ]
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
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/routes/commentsApi.ts"
    }
  ]
}
---

# Members edit only their own comments

Editing someone else's comment is refused, for admins and owners too.
