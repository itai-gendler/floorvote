---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "member-account",
      "effect": "changes",
      "from": "Pending invite",
      "to": "Active"
    }
  ],
  "permits": [
    {
      "actors": [
        "visitor"
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
      "target": "api/src/lib/pendingInvite.ts"
    }
  ]
}
---

# A pending invite becomes an active member only when the invited person signs in

Nobody can accept an invite on someone else's behalf; the first sign-in through any of the person's links ends the pending invite.
