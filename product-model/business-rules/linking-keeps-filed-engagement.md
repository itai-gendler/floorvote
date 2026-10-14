---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "link-draft-bill",
      "contexts": [
        {
          "place": "instance-web::workspace"
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

# Linking a draft keeps the filed bill's engagement where both have it

A member's vote or note, the official position and each custom field value move from the draft only where the filed bill has none; otherwise the filed bill's is kept and the draft's is discarded. Comments, notifications, feed activity and calendar links always move.
