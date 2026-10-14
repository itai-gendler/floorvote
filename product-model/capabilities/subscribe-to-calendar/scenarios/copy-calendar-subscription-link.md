---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Standard member opens the subscribe options on the calendar",
      "kind": "actor",
      "actor": "standard-member",
      "entities": [],
      "contexts": {
        "web": {
          "place": "instance-web::workspace::calendar"
        }
      }
    },
    {
      "text": "The Product gives the calendar feed link as a web address, a webcal link and a Google Calendar link, creating the secret link the first time anyone asks",
      "kind": "product",
      "actor": "standard-member",
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
        "web": {
          "place": "instance-web::workspace::calendar"
        }
      }
    },
    {
      "text": "The Standard member adds the link where they keep their own calendar",
      "kind": "actor",
      "actor": "standard-member",
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
        "web": {
          "place": "instance-web::workspace::calendar"
        }
      }
    }
  ]
}
---

# Subscribe from a calendar app

## Trigger

A member wants the team's hearings in the calendar they already use.

## Outcome

The member's calendar app shows the team calendar and keeps it current.
