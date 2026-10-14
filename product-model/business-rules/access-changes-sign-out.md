---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "change-permission-level"
    },
    {
      "type": "capability",
      "id": "deactivate-member-account"
    },
    {
      "type": "capability",
      "id": "deactivate-own-account"
    }
  ],
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

# Changing a member's permission level or deactivating them signs them out everywhere

Every session of the member ends at once, so the change applies on their next request. Restricting voting signs nobody out.
