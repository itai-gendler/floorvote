---
{
  "availability": [
    {
      "place": "instance-web::settings"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/pages/admin/Notifications.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/routes/adminApi.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "shared/modules.ts"
    }
  ]
}
---

# Change notification settings

An admin sets the instance-wide emails: whether mentions and replies are emailed, whether the digest goes out daily or weekly and on which day, and whether and on which day the week-ahead email goes out. Members can still opt out of each for themselves.
