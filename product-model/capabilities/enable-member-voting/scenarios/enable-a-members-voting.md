---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Admin turns voting back on for a member",
      "kind": "actor",
      "actor": "admin",
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
          "place": "instance-web::settings::members"
        }
      }
    },
    {
      "text": "The Product allows the member account to vote",
      "kind": "product",
      "actor": "admin",
      "entities": [
        {
          "entity": "member-account",
          "effect": "changes",
          "facts": [
            "Voting"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "instance-web::settings::members"
        }
      }
    }
  ]
}
---

# Allow a member's voting

## Trigger

A member's role on the team changes.

## Outcome

The member can vote, and tallies count their votes again.
