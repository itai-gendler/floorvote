---
{
  "availability": [
    {
      "place": "instance-web::workspace"
    }
  ],
  "domain": "account",
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/routes/users.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/pages/Profile.tsx"
    }
  ]
}
---

# Delete own account

While account deletion is on, a member permanently deletes their own account with all its votes, comments, reactions and notes.
