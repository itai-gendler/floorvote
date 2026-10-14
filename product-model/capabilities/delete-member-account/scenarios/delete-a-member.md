---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "Account deletion is on for the instance",
      "kind": "condition",
      "actor": "admin",
      "entities": [
        {
          "entity": "instance-settings",
          "effect": "reads",
          "facts": [
            "Account deletion"
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
      "text": "The Admin deletes another member's account",
      "kind": "actor",
      "actor": "admin",
      "entities": [
        {
          "entity": "member-account",
          "effect": "reads",
          "facts": [
            "Name"
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
      "text": "The Product removes the member account with its votes, comments, reactions and personal notes",
      "kind": "product",
      "actor": "admin",
      "entities": [
        {
          "entity": "member-account",
          "effect": "removes",
          "from": "Active"
        },
        {
          "entity": "member-vote",
          "effect": "removes",
          "with": "member-account"
        },
        {
          "entity": "comment",
          "effect": "removes",
          "with": "member-account"
        },
        {
          "entity": "reaction",
          "effect": "removes",
          "with": "member-account"
        },
        {
          "entity": "personal-note",
          "effect": "removes",
          "with": "member-account"
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

# Delete a member

## Trigger

A person asks for their data to be removed.

## Outcome

The account and its activity are gone for good.
