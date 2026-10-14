---
{
  "availability": [
    {
      "place": "instance-web::workspace"
    }
  ],
  "domain": "bills",
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/routes/commentsApi.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/lib/mentions.ts"
    }
  ]
}
---

# Edit comment

A member edits their own comment. Editing never re-notifies people already mentioned; only newly added mentions are notified.
