---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Admin enters a new name for a role",
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
      "text": "The Product renames the role unless another active role has that name or it contains @",
      "kind": "product",
      "actor": "admin",
      "entities": [
        {
          "entity": "role",
          "effect": "changes",
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
    }
  ]
}
---

# Rename a role

## Trigger

A committee is renamed.

## Outcome

The role shows the new name everywhere it appears.
