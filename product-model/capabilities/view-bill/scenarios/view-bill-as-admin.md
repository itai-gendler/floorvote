---
{
  "kind": "alternative",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Admin opens a bill",
      "kind": "actor",
      "actor": "admin",
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
      "text": "The Product shows the bill with each member's vote, when they voted and their roles, alongside the tally",
      "kind": "product",
      "actor": "admin",
      "entities": [
        {
          "entity": "bill",
          "effect": "reads",
          "facts": [
            "Bill number",
            "Title",
            "Vote tally",
            "Official position"
          ]
        },
        {
          "entity": "member-vote",
          "effect": "reads",
          "facts": [
            "Position",
            "Voted at"
          ]
        },
        {
          "entity": "member-account",
          "effect": "reads",
          "facts": [
            "Name",
            "Roles"
          ]
        },
        {
          "entity": "role",
          "effect": "reads",
          "facts": [
            "Name"
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

# See how each member voted

## Trigger

An admin prepares to set the team's official position.

## Outcome

The admin sees who voted how; standard members see only the tally and their own vote.
