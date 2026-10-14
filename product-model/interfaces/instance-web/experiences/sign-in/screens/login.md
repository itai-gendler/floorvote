---
{
  "entities": [
    {
      "entity": "member-account",
      "collects": [
        "Email"
      ]
    }
  ],
  "entryPoints": [
    {
      "instance-web": "/login"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/pages/Login.tsx"
    }
  ]
}
---

# Login

Where a person enters their email address to be sent a sign-in link, or enters a demo instance.
