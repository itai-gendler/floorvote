---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "member-account",
      "effect": "changes",
      "to": "Deactivated"
    }
  ],
  "permits": [
    {
      "related": [
        {
          "verb": "holds",
          "entity": "standard-member"
        }
      ]
    },
    {
      "related": [
        {
          "verb": "holds",
          "entity": "admin"
        }
      ]
    },
    {
      "related": [
        {
          "verb": "holds",
          "entity": "owner"
        }
      ]
    },
    {
      "actors": [
        "admin"
      ],
      "when": [
        {
          "fact": "Permission level",
          "is-not": "Owner"
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
      "target": "api/src/routes/adminApi.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/routes/users.ts"
    }
  ]
}
---

# Members deactivate their own account; admins deactivate non-owners and owners deactivate anyone

Any member may deactivate their own account. Deactivating an owner is refused to anyone but an owner.
