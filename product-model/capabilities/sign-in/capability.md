---
{
  "availability": [
    {
      "place": "instance-web::sign-in"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/routes/auth.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/pages/Login.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/pages/AuthVerify.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/lib/email.ts"
    }
  ]
}
---

# Sign in

A person signs in by asking for a link at their email address and following the link they are emailed. The same link page signs in an invited person the first time they follow their invite. A demo instance lets visitors in without a link.
