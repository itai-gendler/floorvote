---
{
  "entities": [
    {
      "entity": "notification",
      "shows": [
        "Kind",
        "Reached through",
        "Emoji",
        "Created at"
      ]
    },
    {
      "entity": "comment",
      "shows": [
        "Content"
      ]
    },
    {
      "entity": "bill",
      "shows": [
        "Bill number",
        "Title"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/components/NotificationsSlideOver.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/lib/notifications.ts"
    }
  ]
}
---

# Notifications

The member's notifications panel: mentions and replies newest first, and reactions to their comments grouped one row per comment.
