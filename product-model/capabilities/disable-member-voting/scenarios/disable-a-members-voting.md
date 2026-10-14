---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Admin turns voting off for a member",
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
      "text": "The Product restricts the member account's voting without signing them out",
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

# Restrict a member's voting

## Trigger

A staff member or observer should not count in the team's votes.

## Outcome

The member can no longer vote or clear a vote, and tallies stop counting the votes they already cast.
