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
      "target": "web/src/components/sidebar/MembersPopup.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/components/Sidebar.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/routes/users.ts"
    }
  ]
}
---

# View team members

A standard member opens the team's member list from the sidebar: every member who is not deactivated, with their subtitle, permission level and roles. Admins and owners go to the Members page instead.
