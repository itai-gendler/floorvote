---
{
  "kind": "alternative",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Admin selects bills, or keeps the current filter, and sets one priority for all of them",
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
          "place": "instance-web::workspace::bills"
        }
      }
    },
    {
      "text": "The Product sets the priority on every selected bill, triages the new matches among them and starts tracking any untracked ones",
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
          "place": "instance-web::workspace::bills"
        }
      }
    }
  ]
}
---

# Prioritize many bills at once

## Trigger

An admin works through a batch of bills after a filing deadline.

## Outcome

Every selected bill has the priority; more than ten bills appear in the feed as one bulk entry.

## Edge cases

- A selection of more than 1,000 bills is refused until filters narrow it.
