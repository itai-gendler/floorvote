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

# Resend invite

An admin sends a pending invite a new invite, valid for seven days.
