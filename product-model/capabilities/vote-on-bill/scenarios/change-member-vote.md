---
{
  "kind": "alternative",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Standard member chooses a different position on a bill they voted on",
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
      "text": "The Product replaces the member's vote with the new position",
      "kind": "product",
      "actor": "standard-member",
      "entities": [
        {
          "entity": "member-vote",
          "effect": "changes",
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

# Change your vote

## Trigger

A member changes their mind after discussion.

## Outcome

The member still has one vote on the bill, with the new position.
