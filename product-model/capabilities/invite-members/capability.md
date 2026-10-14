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
      "target": "api/src/routes/adminApi.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/queue/inviteEmails.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/lib/memberAddress.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/lib/bouncedAddresses.ts"
    }
  ]
}
---

# Invite members

An admin invites up to 500 people at once, as standard members or admins. Each gets an invite email valid for seven days and shows as a pending invite until they sign in.
