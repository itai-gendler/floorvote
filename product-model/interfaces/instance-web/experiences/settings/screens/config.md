---
{
  "entities": [
    {
      "entity": "instance-settings",
      "shows": [
        "Name",
        "Organization noun",
        "Keywords",
        "AI context",
        "Relevance question",
        "Tag taxonomy",
        "New match minimum relevance",
        "Calendar feed link"
      ],
      "collects": [
        "Name",
        "Organization noun",
        "Keywords",
        "AI context",
        "Relevance question",
        "Tag taxonomy",
        "New match minimum relevance"
      ]
    },
    {
      "entity": "custom-field",
      "shows": [
        "Name",
        "Type",
        "Options",
        "Multiple",
        "Pinned",
        "Order"
      ],
      "collects": [
        "Name",
        "Type",
        "Options",
        "Multiple",
        "Pinned"
      ]
    }
  ],
  "entryPoints": [
    {
      "instance-web": "/admin/config"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/pages/admin/Config.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/pages/admin/KeywordMatchSummary.tsx"
    }
  ]
}
---

# Config

The instance's configuration: bill keywords with live match counts, AI instructions, the New matches threshold, custom fields, labels, the calendar link, data export and other operations.
