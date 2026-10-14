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
      "target": "api/src/lib/reactions.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "shared/reactionEmojis.ts"
    }
  ]
}
---

# Add reaction

A member reacts to a comment with one of the offered emoji. The comment's author is notified in the app, never by email.
