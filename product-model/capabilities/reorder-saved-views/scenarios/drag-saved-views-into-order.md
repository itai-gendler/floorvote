---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Admin drags a saved view to a new place in the switcher",
      "kind": "actor",
      "actor": "admin",
      "entities": [
        {
          "entity": "saved-view",
          "effect": "reads",
          "facts": [
            "Name"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "instance-web::workspace::bills"
        }
      }
    },
    {
      "text": "The Product saves the new order for everyone",
      "kind": "product",
      "actor": "admin",
      "entities": [
        {
          "entity": "saved-view",
          "effect": "changes",
          "facts": [
            "Order"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "instance-web::workspace::bills"
        }
      }
    }
  ]
}
---

# Reorder saved views

## Trigger

The views the team uses most should come first.

## Outcome

Every member sees the saved views in the new order.
