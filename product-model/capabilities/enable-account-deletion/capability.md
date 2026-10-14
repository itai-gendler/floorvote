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
      "target": "api/src/lib/accountDeletion.ts"
    }
  ]
}
---

# Enable account deletion

An owner allows accounts to be deleted permanently: owners and admins can delete accounts, and members can delete their own.
