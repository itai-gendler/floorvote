---
{
  "availability": [
    {
      "place": "instance-web::settings"
    }
  ],
  "domain": "members",
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/lib/inviteBounces.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/lib/inviteBounceEmail.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/index.ts"
    }
  ]
}
---

# Report bounced invites

Every hour the instance checks whether invite or sign-in emails to pending invites bounced, marks those invites "Email bounced" and emails whoever should fix them.
