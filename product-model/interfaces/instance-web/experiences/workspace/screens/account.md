---
{
  "entities": [
    {
      "entity": "member-account",
      "shows": [
        "Email",
        "Name",
        "Subtitle",
        "Permission level",
        "Roles",
        "Digest emails",
        "Week-ahead emails",
        "Reply emails"
      ],
      "collects": [
        "Name",
        "Subtitle",
        "Digest emails",
        "Week-ahead emails",
        "Reply emails"
      ]
    },
    {
      "entity": "login-activity",
      "shows": [
        "Event",
        "Link kind",
        "Changed by",
        "Country",
        "When"
      ]
    }
  ],
  "entryPoints": [
    {
      "instance-web": "/profile"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/pages/Profile.tsx"
    }
  ]
}
---

# Account

The member's own account: their name and subtitle, the emails they receive, their login activity, and deactivating or deleting the account.
