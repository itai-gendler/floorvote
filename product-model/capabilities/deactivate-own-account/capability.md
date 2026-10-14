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

# Deactivate own account

A member deactivates their own account. They are signed out at once, and only an admin can reactivate them.
