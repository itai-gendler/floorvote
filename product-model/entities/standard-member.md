---
{
  "kind": "person",
  "acts": "external",
  "relations": [
    {
      "entity": "member-account",
      "verb": "holds",
      "cardinality": "one-to-one"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/middleware/auth.ts"
    }
  ]
}
---

# Standard member

The default permission level: follows bills, votes when voting is allowed, comments, keeps personal notes and can be mentioned, with no administrative access.
