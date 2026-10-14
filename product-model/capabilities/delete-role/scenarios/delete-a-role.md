---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Admin deletes a role",
      "kind": "actor",
      "actor": "admin",
      "entities": [
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
          "place": "instance-web::settings::members"
        }
      }
    },
    {
      "text": "The Product removes the role and every member from it",
      "kind": "product",
      "actor": "admin",
      "entities": [
        {
          "entity": "role",
          "effect": "removes"
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

# Delete a role

## Trigger

A group no longer exists.

## Outcome

The role can no longer be mentioned; creating a role with its name later restores it, without its former members.
