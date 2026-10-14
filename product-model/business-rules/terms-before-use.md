---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "accept-terms"
    },
    {
      "type": "capability",
      "id": "sign-in"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/middleware/auth.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/lib/termsAcceptance.ts"
    }
  ]
}
---

# Members accept the current legal terms before using the instance

Where the operator publishes legal terms, a member who has not accepted terms dated on or after the current ones is refused everything but accepting them. Where no terms are published, nothing is asked.
