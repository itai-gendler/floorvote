---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "member-vote",
      "effect": "reads",
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
      "target": "api/src/routes/billsApi/detail.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/routes/billsApi/listRoutes.ts"
    }
  ]
}
---

# Members see their own vote; admins and owners see everyone's

Standard members see the tally and their own vote. Admins and owners also see how each member voted, when, and the member's roles.
