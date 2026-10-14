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

# Enable member voting

An admin lets a member whose voting was restricted vote again.
