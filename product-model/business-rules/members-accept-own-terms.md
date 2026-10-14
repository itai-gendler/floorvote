---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "member-account",
      "effect": "changes",
      "facts": [
        "Accepted terms"
      ]
    }
  ],
  "permits": [
    {
      "related": [
        {
          "verb": "holds",
          "entity": "standard-member"
        }
      ]
    },
    {
      "related": [
        {
          "verb": "holds",
          "entity": "admin"
        }
      ]
    },
    {
      "related": [
        {
          "verb": "holds",
          "entity": "owner"
        }
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

# Members accept the legal terms for themselves

Each acceptance is recorded for the member who accepted, against the terms date current at the time.
