---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Admin chooses to email a member a link to sign in",
      "kind": "actor",
      "actor": "admin",
      "entities": [
        {
          "entity": "member-account",
          "effect": "reads",
          "facts": [
            "Email"
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
      "text": "The Product creates a sign-in link for the member and emails it",
      "kind": "product",
      "actor": "admin",
      "entities": [
        {
          "entity": "sign-in-link",
          "effect": "creates",
          "to": "Active",
          "facts": [
            "Kind",
            "Expires"
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

# Send a member a sign-in link

## Trigger

A member cannot get a sign-in link to arrive on their own.

## Outcome

The member receives a sign-in link; a deactivated member cannot be sent one.
