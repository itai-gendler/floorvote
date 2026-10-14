---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Admin names a new role",
      "kind": "actor",
      "actor": "admin",
      "entities": [
        {
          "entity": "role",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "web": {
          "place": "instance-web::settings::members"
        }
      }
    },
    {
      "text": "The Product creates the role, refusing a name an active role already has, ignoring case, or one containing @",
      "kind": "product",
      "actor": "admin",
      "entities": [
        {
          "entity": "role",
          "effect": "creates",
          "facts": [
            "Name",
            "Members"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "instance-web::settings::members"
        }
      }
    }
  ]
}
---

# Create a role

## Trigger

The team wants to reach a group, such as a committee, with one mention.

## Outcome

The role exists and members can be added to it.
