---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "post-comment"
    },
    {
      "type": "capability",
      "id": "send-email-digest"
    },
    {
      "type": "capability",
      "id": "send-week-ahead-email"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/lib/mentions.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/lib/replies.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/lib/digest.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/lib/weekAhead.ts"
    }
  ]
}
---

# Role mentions, @everyone, replies and scheduled emails skip pending invites and deactivated members

Mentioning a role or everyone, reply notifications, the digest and the week-ahead email reach active members who have accepted their invite; pending invites and deactivated members are skipped. A member mentioned by name is always notified.
