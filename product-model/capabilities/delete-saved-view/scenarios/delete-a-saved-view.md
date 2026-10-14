---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Admin deletes a saved view",
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
      "text": "The Product removes the saved view from the switcher",
      "kind": "product",
      "actor": "admin",
      "entities": [
        {
          "entity": "saved-view",
          "effect": "removes"
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

# Delete a saved view

## Trigger

A view is no longer useful.

## Outcome

Nobody sees the saved view any more.
