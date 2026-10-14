---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "member-account",
      "effect": "removes"
    }
  ],
  "permits": [
    {
      "related": [
        {
          "verb": "holds",
          "entity": "standard-member"
        }
      ],
      "when": [
        {
          "entity": "instance-settings",
          "fact": "Account deletion",
          "is": "On"
        }
      ]
    },
    {
      "related": [
        {
          "verb": "holds",
          "entity": "admin"
        }
      ],
      "when": [
        {
          "entity": "instance-settings",
          "fact": "Account deletion",
          "is": "On"
        }
      ]
    },
    {
      "related": [
        {
          "verb": "holds",
          "entity": "owner"
        }
      ],
      "when": [
        {
          "entity": "instance-settings",
          "fact": "Account deletion",
          "is": "On"
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
        },
        {
          "entity": "instance-settings",
          "fact": "Account deletion",
          "is": "On"
        }
      ]
    },
    {
      "actors": [
        "owner"
      ],
      "when": [
        {
          "entity": "instance-settings",
          "fact": "Account deletion",
          "is": "On"
        }
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/lib/accountDeletion.ts"
    }
  ]
}
---

# Accounts are deleted only while account deletion is on

While an owner has account deletion on, members delete their own account, admins delete other non-owner accounts and owners delete any other account. With it off, every deletion is refused and accounts can only be deactivated.
