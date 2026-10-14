---
{
  "entities": [
    {
      "entity": "sign-in-link",
      "shows": [
        "Kind"
      ]
    },
    {
      "entity": "member-account",
      "shows": [
        "Email"
      ]
    }
  ],
  "entryPoints": [
    {
      "instance-web": "/auth/verify"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/pages/AuthVerify.tsx"
    }
  ]
}
---

# Sign-in link

Where an emailed sign-in link or invite lands: it says whether the link still works and signs the person in when they continue.
