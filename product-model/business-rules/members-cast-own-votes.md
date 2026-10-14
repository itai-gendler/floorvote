---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "member-vote",
      "effect": "creates"
    }
  ],
  "permits": [
    {
      "related": [
        {
          "verb": "casts",
          "entity": "member-account"
        },
        {
          "verb": "holds",
          "entity": "standard-member"
        }
      ],
      "when": [
        {
          "entity": "member-account",
          "fact": "Voting",
          "is": "Allowed"
        }
      ]
    },
    {
      "related": [
        {
          "verb": "casts",
          "entity": "member-account"
        },
        {
          "verb": "holds",
          "entity": "admin"
        }
      ],
      "when": [
        {
          "entity": "member-account",
          "fact": "Voting",
          "is": "Allowed"
        }
      ]
    },
    {
      "related": [
        {
          "verb": "casts",
          "entity": "member-account"
        },
        {
          "verb": "holds",
          "entity": "owner"
        }
      ],
      "when": [
        {
          "entity": "member-account",
          "fact": "Voting",
          "is": "Allowed"
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

# Members whose voting is allowed cast their own votes

Every member votes for themselves only, and only while their voting is allowed.
