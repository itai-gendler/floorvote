---
{
  "kind": "alternative",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Admin sets a priority on a bill the instance does not track",
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
      "text": "The Product saves the priority, starts tracking the bill as added by hand and asks for its full text and AI analysis",
      "kind": "product",
      "actor": "admin",
      "entities": [
        {
          "entity": "bill",
          "effect": "changes",
          "from": "Untracked",
          "to": "Added",
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

# Prioritize an untracked bill

## Trigger

An admin finds a relevant bill that the keywords missed.

## Outcome

The bill is tracked, and its summary, tags and relevance arrive once analysis runs; in a demo, no analysis starts.
