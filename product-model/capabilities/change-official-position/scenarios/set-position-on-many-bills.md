---
{
  "kind": "alternative",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Admin selects bills on the Bills page and sets one official position for all of them",
      "kind": "actor",
      "actor": "admin",
      "entities": [
        {
          "entity": "bill",
          "effect": "reads",
          "facts": [
            "Official position"
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
      "text": "The Product sets the position on every selected bill",
      "kind": "product",
      "actor": "admin",
      "entities": [
        {
          "entity": "bill",
          "effect": "changes",
          "facts": [
            "Official position"
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

# Set a position on many bills

## Trigger

A coalition agrees a position on a package of bills.

## Outcome

Every selected bill has the position; more than ten bills appear in the feed as one bulk entry.

## Edge cases

- A selection of more than 1,000 bills is refused until filters narrow it.
