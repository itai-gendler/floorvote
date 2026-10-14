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
      "target": "web/src/components/ChangeEmailDialog.tsx"
    }
  ]
}
---

# Change invite address

An admin corrects a pending invite's email address and sends a new invite to it in one step. Only a pending invite's address can be changed.
