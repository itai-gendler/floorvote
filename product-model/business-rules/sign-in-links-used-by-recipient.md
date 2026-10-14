---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "sign-in-link",
      "effect": "changes",
      "to": "Used"
    }
  ],
  "permits": [
    {
      "actors": [
        "visitor"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/routes/auth.ts"
    }
  ]
}
---

# A sign-in link is used by the person who follows it

Following an emailed link or invite is what uses it; nobody else can use it up on their behalf.
