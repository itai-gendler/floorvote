---
{
  "availability": [
    {
      "place": "instance-web::workspace"
    },
    {
      "place": "instance-web::settings"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/routes/users.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/routes/adminApi.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/lib/authEvents.ts"
    }
  ]
}
---

# View login activity

A member reviews their own login history, and an admin reviews any member's to help with sign-in trouble, including whether emails to them were delivered.
