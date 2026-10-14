---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Admin changes a custom event's details",
      "kind": "actor",
      "actor": "admin",
      "entities": [
        {
          "entity": "custom-event",
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
      "text": "The Product saves the custom event and raises its sequence so subscribed calendars take the new version",
      "kind": "product",
      "actor": "admin",
      "entities": [
        {
          "entity": "custom-event",
          "effect": "changes",
          "facts": [
            "Title",
            "Date",
            "Time",
            "Location",
            "Details",
            "Link",
            "Bills"
          ]
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

# Edit a custom event

## Trigger

A team meeting moves.

## Outcome

The calendar and subscribed calendar apps show the updated custom event; only custom events can be edited.
