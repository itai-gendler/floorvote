---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "post-comment",
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
      "target": "api/src/lib/mentions.ts"
    }
  ]
}
---

# Only an admin's or owner's @everyone notifies everyone

An @everyone in a standard member's comment is kept in the text but notifies nobody.
