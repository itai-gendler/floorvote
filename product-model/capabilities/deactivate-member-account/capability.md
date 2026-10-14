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

# Deactivate member account

An admin deactivates a member, signing them out everywhere and hiding their votes, comments and activity until they are reactivated. Only an owner deactivates an owner, and the last active owner can't be deactivated.
