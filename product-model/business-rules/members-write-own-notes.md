---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "personal-note",
      "effect": "creates"
    }
  ],
  "permits": [
    {
      "related": [
        {
          "verb": "keeps",
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
          "verb": "keeps",
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
          "verb": "keeps",
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
      "target": "api/src/routes/billsApi/engagementRoutes.ts"
    }
  ]
}
---

# Members write only their own personal notes

Each member has at most one personal note per bill, and writes only their own.
