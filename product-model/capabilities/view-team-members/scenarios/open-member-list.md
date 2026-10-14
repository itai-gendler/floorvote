---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Standard member opens the member count in the sidebar",
      "kind": "actor",
      "actor": "standard-member",
      "entities": [],
      "contexts": {
        "web": {
          "place": "instance-web::workspace"
        }
      }
    },
    {
      "text": "The Product lists the members who are not deactivated by name, with email, subtitle, permission level and roles",
      "kind": "product",
      "actor": "standard-member",
      "entities": [
        {
          "entity": "member-account",
          "effect": "reads",
          "facts": [
            "Name",
            "Email",
            "Subtitle",
            "Permission level",
            "Roles"
          ]
        },
        {
          "entity": "role",
          "effect": "reads",
          "facts": [
            "Name"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "instance-web::workspace"
        }
      }
    }
  ]
}
---

# Open the member list

## Trigger

A member wants to know who is on the team, or which role to mention.

## Outcome

The member sees the team and its roles.
