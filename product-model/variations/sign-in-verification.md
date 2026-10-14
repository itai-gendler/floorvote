---
{
  "kind": "configuration",
  "of": "capability-scenario",
  "settings": [
    {
      "entity": "instance-settings",
      "fact": "Sign-in verification"
    }
  ],
  "takesEffect": "On each request for a sign-in link. The operator turns verification on or off with the deployment.",
  "stability": "Links already sent keep working whichever way verification is set.",
  "alternatives": [
    {
      "id": "sign-in-with-emailed-link",
      "selectedWhen": "Sign-in verification is off, which is the default until the operator configures it: the member asks for a link with their address alone."
    },
    {
      "id": "sign-in-with-verification",
      "selectedWhen": "Sign-in verification is on: the member must pass the verification check with their request."
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "shared/turnstile.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/routes/auth.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/pages/Login.tsx"
    }
  ]
}
---

# Sign-in verification

Operators can put a human verification check in front of sign-in requests; instances without one keep the plain email form. Both are supported.
