---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Admin deletes a custom event",
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
      "text": "The Product marks the custom event cancelled and raises its sequence",
      "kind": "product",
      "actor": "admin",
      "entities": [
        {
          "entity": "custom-event",
          "effect": "changes",
          "from": "Confirmed",
          "to": "Cancelled",
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

# Cancel a custom event

## Trigger

A team meeting is called off.

## Outcome

The custom event shows as cancelled for two days, then drops off the calendar and out of subscriptions.
