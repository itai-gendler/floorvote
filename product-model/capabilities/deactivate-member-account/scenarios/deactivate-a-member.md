---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Admin deactivates a member",
      "kind": "actor",
      "actor": "admin",
      "entities": [
        {
          "entity": "member-account",
          "effect": "reads",
          "facts": [
            "Name"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "instance-web::settings::members"
        }
      }
    },
    {
      "text": "The Product deactivates the member account and ends every session of it",
      "kind": "product",
      "actor": "admin",
      "entities": [
        {
          "entity": "member-account",
          "effect": "changes",
          "from": "Active",
          "to": "Deactivated",
          "facts": []
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

# Deactivate a member

## Trigger

Someone leaves the team.

## Outcome

The member cannot sign in, and their votes, comments and feed activity are hidden from the team.
