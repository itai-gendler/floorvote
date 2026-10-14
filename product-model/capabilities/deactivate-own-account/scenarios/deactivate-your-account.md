---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Standard member chooses Deactivate my account and confirms",
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
      "text": "The Product deactivates the member account and ends every session of it",
      "kind": "product",
      "actor": "standard-member",
      "entities": [
        {
          "entity": "member-account",
          "effect": "changes",
          "from": "Active",
          "to": "Deactivated",
          "facts": []
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

# Deactivate your account

## Trigger

A member steps away from the team.

## Outcome

The member is signed out, and their activity is hidden until an admin reactivates them.

## Edge cases

- The last active owner is told to transfer ownership first.
