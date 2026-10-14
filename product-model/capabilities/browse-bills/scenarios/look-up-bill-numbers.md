---
{
  "kind": "alternative",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Standard member pastes several bill numbers separated by commas into the search",
      "kind": "actor",
      "actor": "standard-member",
      "entities": [
        {
          "entity": "bill",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "web": {
          "place": "instance-web::workspace::bills"
        }
      }
    },
    {
      "text": "The Product returns every bill matching any of the terms, with bill-number matches first",
      "kind": "product",
      "actor": "standard-member",
      "entities": [
        {
          "entity": "bill",
          "effect": "reads",
          "facts": [
            "Bill number",
            "Title",
            "State",
            "Status",
            "Priority"
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

# Look up a batch of bills

## Trigger

A member has a list of bill numbers from a meeting agenda or a coalition email.

## Outcome

The whole batch appears in one list, exact bill-number matches on top.
