---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "view-bill"
    },
    {
      "type": "capability",
      "id": "browse-feed"
    },
    {
      "type": "capability",
      "id": "view-notifications"
    },
    {
      "type": "capability",
      "id": "send-email-digest"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/lib/accountDeletion.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/routes/feed.ts"
    }
  ]
}
---

# A deactivated member's comments, reactions and activity are hidden until they are reactivated

Deactivation keeps everything the member did, hidden from bill pages, the feed, notifications and the digest; reactivation shows it again.
