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

# Change account settings

A member changes how they appear to the team and which emails they receive: their name and subtitle, the digest, the week-ahead email and reply emails.
