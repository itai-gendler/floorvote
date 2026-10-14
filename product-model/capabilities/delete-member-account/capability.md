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

# Delete member account

While account deletion is on, an admin permanently deletes a member's account with all its votes, comments, reactions and notes. Only an owner deletes an owner; nobody deletes their own account from here.
