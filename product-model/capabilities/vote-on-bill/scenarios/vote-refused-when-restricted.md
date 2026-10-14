---
{
  "kind": "validation",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Standard member whose voting is restricted tries to vote on a bill",
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
      "text": "The member account's voting is restricted",
      "kind": "condition",
      "actor": "standard-member",
      "entities": [
        {
          "entity": "member-account",
          "effect": "reads",
          "facts": [
            "Voting"
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
      "text": "The Product refuses: the member is not eligible to vote",
      "kind": "product",
      "actor": "standard-member",
      "entities": [],
      "contexts": {
        "web": {
          "place": "instance-web::workspace::bill"
        }
      }
    }
  ]
}
---

# Voting is restricted

## Trigger

An admin restricted a member's voting, for someone who should follow and discuss bills without casting an official vote.

## Outcome

No vote is recorded.
