---
{
  "kind": "alternative",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Admin turns on the New matches filter",
      "kind": "actor",
      "actor": "admin",
      "entities": [],
      "contexts": {
        "web": {
          "place": "instance-web::workspace::bills"
        }
      }
    },
    {
      "text": "The Product lists analyzed keyword matches nobody has triaged yet whose relevance reaches the instance's threshold",
      "kind": "product",
      "actor": "admin",
      "entities": [
        {
          "entity": "instance-settings",
          "effect": "reads",
          "facts": [
            "New match minimum relevance"
          ]
        },
        {
          "entity": "bill",
          "effect": "reads",
          "facts": [
            "Bill number",
            "Title",
            "Summary",
            "Relevance score",
            "New match"
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

# Review new matches

## Trigger

New keyword matches are waiting for a decision.

## Outcome

The admin sees the worklist of new matches to prioritize or dismiss.

## Edge cases

- With the threshold at 0, a match without a relevance score still appears; a higher threshold holds it back until it is scored.
