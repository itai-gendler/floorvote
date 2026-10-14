---
{
  "availability": [
    {
      "place": "instance-web::workspace"
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
      "target": "api/src/middleware/auth.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/components/AcceptTerms.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/lib/termsAcceptance.ts"
    }
  ]
}
---

# Accept terms

A member accepts the instance's current legal terms. This exists only where the operator publishes legal terms; until a member has accepted the current terms, the instance refuses everything else they try.
