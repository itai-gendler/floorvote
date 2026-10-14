---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Admin enters a title, a date and optionally a time, location, details, link and bills",
      "kind": "actor",
      "actor": "admin",
      "entities": [
        {
          "entity": "bill",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "web": {
          "place": "instance-web::workspace::calendar"
        }
      }
    },
    {
      "text": "The Product adds the custom event to the calendar, keeping only bills the instance has",
      "kind": "product",
      "actor": "admin",
      "entities": [
        {
          "entity": "custom-event",
          "effect": "creates",
          "to": "Confirmed",
          "facts": [
            "Title",
            "Date",
            "Time",
            "Location",
            "Details",
            "Link",
            "Bills"
          ]
        },
        {
          "entity": "bill",
          "effect": "reads",
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

# Add a custom event

## Trigger

The team has a meeting or deadline of its own.

## Outcome

Everyone sees the custom event on the calendar and in subscribed calendar apps, and the week-ahead email lists it.

## Edge cases

- A missing title or date is refused.
- A link that is not a web address is refused.
