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
      "actor": "standard-member",
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
          "place": "instance-web::workspace::account"
        }
      }
    },
    {
      "text": "The Standard member chooses to delete their account and confirms",
      "kind": "actor",
      "actor": "standard-member",
      "entities": [
        {
          "entity": "member-account",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "web": {
          "place": "instance-web::workspace::account"
        }
      }
    },
    {
      "text": "The Product removes the member account with its votes, comments, reactions and personal notes",
      "kind": "product",
      "actor": "standard-member",
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
          "place": "instance-web::workspace::account"
        }
      }
    }
  ]
}
---

# Delete your account

## Trigger

A member wants their data gone.

## Outcome

The account and its activity are gone for good.

## Edge cases

- The last active owner is told to transfer ownership first.
