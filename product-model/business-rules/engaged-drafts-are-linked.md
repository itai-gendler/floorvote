---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "delete-draft-bill",
      "contexts": [
        {
          "place": "instance-web::workspace"
        },
        {
          "place": "instance-web::settings"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/routes/billsApi/draftRoutes.ts"
    }
  ]
}
---

# A draft with votes, a position, comments or notes is linked, never deleted

Deleting such a draft is refused with a pointer to linking it to its filed bill, so the team's engagement is never lost with it.
