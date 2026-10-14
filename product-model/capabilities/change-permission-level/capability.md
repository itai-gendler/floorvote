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
      "target": "api/src/lib/owners.ts"
    }
  ]
}
---

# Change permission level

An admin makes a member a Standard member or an Admin; only an owner makes someone an Owner or changes an owner's level. The member is signed out everywhere so the change applies at once.
