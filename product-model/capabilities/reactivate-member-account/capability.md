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
    }
  ]
}
---

# Reactivate member account

An admin reactivates a deactivated member, bringing their votes, comments and activity back into view.
