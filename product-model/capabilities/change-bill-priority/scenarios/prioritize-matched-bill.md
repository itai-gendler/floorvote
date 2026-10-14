---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Admin sets a tracked bill's priority to high, medium or low",
      "kind": "actor",
      "actor": "admin",
      "entities": [
        {
          "entity": "bill",
          "effect": "reads",
          "facts": [
            "Priority"
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
      "text": "The Product saves the priority and, the first time, records the bill as triaged by this admin",
      "kind": "product",
      "actor": "admin",
      "entities": [
        {
          "entity": "bill",
          "effect": "changes",
          "facts": [
            "Priority",
            "Triaged"
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

# Prioritize a tracked bill

## Trigger

An admin decides a bill deserves the team's attention.

## Outcome

The bill shows its priority everywhere, leaves the New matches worklist for good, and its hearings appear on the calendar.
