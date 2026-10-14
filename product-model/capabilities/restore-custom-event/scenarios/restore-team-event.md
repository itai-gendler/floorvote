---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Admin restores a cancelled custom event",
      "kind": "actor",
      "actor": "admin",
      "entities": [
        {
          "entity": "custom-event",
          "effect": "reads",
          "facts": [
            "Title"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "instance-web::workspace::calendar"
        }
      }
    },
    {
      "text": "The Product confirms the custom event again and raises its sequence",
      "kind": "product",
      "actor": "admin",
      "entities": [
        {
          "entity": "custom-event",
          "effect": "changes",
          "from": "Cancelled",
          "to": "Confirmed",
          "facts": []
        }
      ],
      "contexts": {
        "web": {
          "place": "instance-web::workspace::calendar"
        }
      }
    }
  ]
}
---

# Restore a custom event

## Trigger

A cancelled meeting is back on.

## Outcome

The custom event is on the calendar and in subscriptions again.
