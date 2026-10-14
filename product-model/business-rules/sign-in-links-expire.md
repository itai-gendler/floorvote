---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "sign-in"
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
      "target": "api/src/queue/inviteEmails.ts"
    }
  ]
}
---

# A sign-in link works once, within 60 minutes, and an invite within seven days

Following a link uses it up. A member holds at most five unused, unexpired sign-in links at a time; asking for more sends nothing. A session lasts 30 days and renews while the member uses the instance.
