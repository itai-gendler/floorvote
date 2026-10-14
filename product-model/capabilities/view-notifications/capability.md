---
{
  "availability": [
    {
      "place": "instance-web::workspace"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/routes/notificationsApi.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/lib/notifications.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/components/NotificationsSlideOver.tsx"
    }
  ]
}
---

# View notifications

A member opens their notifications panel to see mentions, replies and reactions to their comments. Opening the panel marks everything read; opening a bill marks that bill's notifications read.
