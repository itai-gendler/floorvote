---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "sign-in"
    },
    {
      "type": "capability",
      "id": "sign-out"
    },
    {
      "type": "capability",
      "id": "invite-members"
    },
    {
      "type": "capability",
      "id": "resend-invite"
    },
    {
      "type": "capability",
      "id": "send-sign-in-link"
    },
    {
      "type": "capability",
      "id": "change-invite-address"
    },
    {
      "type": "entity",
      "id": "login-activity"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/lib/authEvents.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/routes/auth.ts"
    }
  ]
}
---

# A member's login activity records their sign-in links and sign-ins

Each link requested or emailed, each sign-in and failed sign-in with its reason, each sign-out and each invite address change, with who made the change, is recorded with the request's country and browser. Requests from unknown addresses are recorded apart, for admins.
