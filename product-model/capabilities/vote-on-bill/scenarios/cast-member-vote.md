---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Standard member chooses support, oppose or neutral on a bill",
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
          "place": "instance-web::workspace::bill"
        }
      }
    },
    {
      "text": "The Product records the member's vote",
      "kind": "product",
      "actor": "standard-member",
      "entities": [
        {
          "entity": "member-vote",
          "effect": "creates",
          "facts": [
            "Position",
            "Voted at"
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

# Vote on a bill

## Trigger

A member has made up their mind about a bill.

## Outcome

The bill's tally counts the vote, and the bill leaves the member's Not voted list and sidebar reminder.

## Edge cases

- The Prioritized bills widget in the sidebar offers the same three choices on each prioritized bill.
