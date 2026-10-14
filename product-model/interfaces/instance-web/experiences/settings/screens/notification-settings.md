---
{
  "entities": [
    {
      "entity": "instance-settings",
      "shows": [
        "Conversation emails",
        "Email digest",
        "Week-ahead email"
      ],
      "collects": [
        "Conversation emails",
        "Email digest",
        "Week-ahead email"
      ]
    }
  ],
  "entryPoints": [
    {
      "instance-web": "/admin/notifications"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/pages/admin/Notifications.tsx"
    }
  ]
}
---

# Notification settings

The instance-wide email settings: conversation emails, the email digest and its cadence, and the week-ahead email and its day.
