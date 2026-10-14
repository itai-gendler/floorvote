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
      "id": "delete-member-account"
    },
    {
      "type": "capability",
      "id": "deactivate-own-account"
    },
    {
      "type": "capability",
      "id": "delete-own-account"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/lib/owners.ts"
    },
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

# An instance always keeps at least one active owner

Demoting, deactivating or deleting the last active owner is refused; the last owner is told to transfer ownership first.
