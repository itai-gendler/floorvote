---
{
  "kind": "validation",
  "routes": {
    "feed": "Calendar feed"
  },
  "steps": [
    {
      "text": "The Calendar app requests the calendar feed at a link that is not the current one",
      "kind": "actor",
      "actor": "calendar-app",
      "entities": [],
      "contexts": {
        "feed": {
          "place": "calendar-feed"
        }
      }
    },
    {
      "text": "The link does not match the instance's calendar feed link",
      "kind": "condition",
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
      "text": "The Product answers that there is no such calendar",
      "kind": "product",
      "actor": "calendar-app",
      "entities": [],
      "contexts": {
        "feed": {
          "place": "calendar-feed"
        }
      }
    }
  ]
}
---

# Fetch with an old link

## Trigger

An admin reset the calendar link, or the link was mistyped.

## Outcome

The calendar app receives nothing.
