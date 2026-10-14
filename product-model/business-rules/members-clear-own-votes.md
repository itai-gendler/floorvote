---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "member-vote",
      "effect": "removes"
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
    },
    {
      "actors": [
        "owner"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/routes/billsApi/engagementRoutes.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/routes/adminApi.ts"
    }
  ]
}
---

# Members whose voting is allowed clear only their own votes

A member clears their own vote while their voting is allowed; a member whose voting is restricted keeps the votes they cast. Removing everyone's votes is part of an owner clearing the team's activity.
