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
      "target": "web/src/components/sidebar/CustomizeSidebar.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/components/Sidebar.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "shared/modules.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/routes/stats.ts"
    }
  ]
}
---

# Customize sidebar

An admin chooses which widgets every member's sidebar shows: Prioritized bills, with a vote reminder on each, and Upcoming hearings for prioritized bills in the next 30 days.
