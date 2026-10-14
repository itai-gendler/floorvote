---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Admin drags a custom field to a new place",
      "kind": "actor",
      "actor": "admin",
      "entities": [
        {
          "entity": "custom-field",
          "effect": "reads",
          "facts": [
            "Name",
            "Order"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "instance-web::settings::config"
        }
      }
    },
    {
      "text": "The Product saves the new order",
      "kind": "product",
      "actor": "admin",
      "entities": [
        {
          "entity": "custom-field",
          "effect": "changes",
          "facts": [
            "Order"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "instance-web::settings::config"
        }
      }
    }
  ]
}
---

# Reorder custom fields

## Trigger

The most-used fields should come first.

## Outcome

Every bill page lists the custom fields in the new order.
