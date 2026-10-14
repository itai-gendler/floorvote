---
{
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
      "target": "api/src/routes/users.ts"
    }
  ]
}
---

# Role

A named group of members an admin defines, such as a committee, which members can @-mention together.

## Information kept

- **Name** — the role's name, unique ignoring case and never containing @
- **Members** — the members who belong to it
