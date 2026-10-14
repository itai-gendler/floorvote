---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "sign-in-link",
      "effect": "creates"
    }
  ],
  "permits": [
    {
      "actors": [
        "visitor"
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
      "target": "api/src/routes/auth.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/routes/adminApi.ts"
    }
  ]
}
---

# Sign-in links are sent at a visitor's request or by an admin or owner

A visitor asks for a link to their own address; admins and owners send invites and sign-in links to members. Links are never sent to deactivated members.
