---
{
  "kind": "primary",
  "routes": {
    "feed": "Calendar feed"
  },
  "steps": [
    {
      "text": "The Calendar app requests the calendar feed at its secret link",
      "kind": "actor",
      "actor": "calendar-app",
      "entities": [
        {
          "entity": "instance-settings",
          "effect": "reads",
          "facts": [
            "Calendar feed link"
          ]
        }
      ],
      "contexts": {
        "feed": {
          "place": "calendar-feed"
        }
      }
    },
    {
      "text": "The Product returns the same events the calendar shows, confirmed ones from the past week onward, each linking back to its bill and timed in its state's time zone",
      "kind": "product",
      "actor": "calendar-app",
      "entities": [
        {
          "entity": "calendar-entry",
          "effect": "reads",
          "facts": [
            "Kind",
            "Date",
            "Time",
            "Location",
            "Description"
          ]
        },
        {
          "entity": "legislature-event",
          "effect": "reads",
          "facts": [
            "Title",
            "Date",
            "Time",
            "Location"
          ]
        },
        {
          "entity": "custom-event",
          "effect": "reads",
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
          "facts": [
            "Bill number",
            "Title",
            "Priority"
          ]
        },
        {
          "entity": "instance-settings",
          "effect": "reads",
          "facts": [
            "Name"
          ]
        }
      ],
      "contexts": {
        "feed": {
          "place": "calendar-feed"
        }
      }
    }
  ]
}
---

# Fetch the calendar feed

## Trigger

A subscribed calendar app refreshes.

## Outcome

The calendar app holds the team calendar titled with the instance's name; a cancelled event shows as cancelled for two days and then drops out.

## Edge cases

- A legislature event the rules hide drops out of the subscription too.
- An event whose state cannot be told uses the time zone of the person who created it, then the operator's default.
