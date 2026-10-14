---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Admin chooses Resend invite for a member",
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
      "text": "The Product creates a new invite and emails it; earlier invites keep working until they expire",
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

# Resend an invite

## Trigger

An invite expired or was lost.

## Outcome

The person has a fresh invite; a deactivated member cannot be sent one.
