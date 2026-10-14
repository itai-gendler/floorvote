---
{
  "kind": "alternative",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Admin clears the official position on a bill",
      "kind": "actor",
      "actor": "admin",
      "entities": [
        {
          "entity": "bill",
          "effect": "reads",
          "facts": [
            "Official position"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "instance-web::workspace::bill"
        }
      }
    },
    {
      "text": "The Product removes the position and hides the earlier position entries from the feed",
      "kind": "product",
      "actor": "admin",
      "entities": [
        {
          "entity": "bill",
          "effect": "changes",
          "facts": [
            "Official position"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "instance-web::workspace::bill"
        }
      }
    }
  ]
}
---

# Clear the official position

## Trigger

A position was set by mistake or no longer stands.

## Outcome

The bill has no official position.
