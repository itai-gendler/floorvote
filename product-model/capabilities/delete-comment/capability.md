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
    }
  ]
}
---

# Delete comment

A member deletes their own comment, or an admin deletes anyone's. The comment, its reactions and its notifications disappear.
