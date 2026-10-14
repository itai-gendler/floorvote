---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "member-vote",
      "effect": "changes",
      "facts": [
        "Position"
      ]
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

# Members whose voting is allowed change only their own votes

Voting again replaces the member's own vote; nobody changes someone else's.
