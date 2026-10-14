---
{
  "kind": "edge",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The hourly run finds that the legislature cancelled one of its events",
      "kind": "condition",
      "unattended": true,
      "entities": [
        {
          "entity": "legislature-event",
          "effect": "reads",
          "facts": [
            "Title",
            "Date"
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
      "text": "The Product marks the legislature event cancelled",
      "kind": "product",
      "entities": [
        {
          "entity": "legislature-event",
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

# The legislature cancels an event

## Trigger

A hearing on the legislature's calendar is called off.

## Outcome

The calendar and subscribed calendars show the event as cancelled.
