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
        "Voting",
        "Roles",
        "Invited by",
        "Last active",
        "Email bounced"
      ],
      "collects": [
        "Email",
        "Name",
        "Permission level",
        "Voting",
        "Roles"
      ]
    },
    {
      "entity": "role",
      "shows": [
        "Name",
        "Members"
      ],
      "collects": [
        "Name"
      ]
    },
    {
      "entity": "login-activity",
      "shows": [
        "Event",
        "Link kind",
        "Changed by",
        "Country",
        "Device",
        "When"
      ]
    },
    {
      "entity": "instance-settings",
      "shows": [
        "Account deletion"
      ]
    }
  ],
  "entryPoints": [
    {
      "instance-web": "/admin/members"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/pages/admin/Members.tsx"
    }
  ]
}
---

# Members

The instance's roster: every member with their permission level, roles, voting and invite status, and the controls to invite, manage and remove members, define roles and set the account deletion policy.
