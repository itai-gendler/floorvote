---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Standard member clears their vote on a bill",
      "kind": "actor",
      "actor": "standard-member",
      "entities": [
        {
          "entity": "member-vote",
          "effect": "reads",
          "facts": [
            "Position"
          ]
        },
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
      "text": "The Product removes the member's vote",
      "kind": "product",
      "actor": "standard-member",
      "entities": [
        {
          "entity": "member-vote",
          "effect": "removes"
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

# Clear your vote

## Trigger

A member no longer wants to take a side on a bill.

## Outcome

The tally no longer counts the member, and the bill is back on their Not voted list.
