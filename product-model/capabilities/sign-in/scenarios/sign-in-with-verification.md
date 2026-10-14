---
{
  "kind": "alternative",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Visitor enters their email address and completes the human verification check",
      "kind": "actor",
      "actor": "visitor",
      "entities": [
        {
          "entity": "member-account",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "web": {
          "place": "instance-web::sign-in::login"
        }
      }
    },
    {
      "text": "The Product confirms the check passed, creates a sign-in link for the matching member account and emails it, valid for 60 minutes",
      "kind": "product",
      "actor": "visitor",
      "entities": [
        {
          "entity": "instance-settings",
          "effect": "reads",
          "facts": [
            "Sign-in verification"
          ]
        },
        {
          "entity": "member-account",
          "effect": "reads",
          "facts": [
            "Email"
          ]
        },
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
          "place": "instance-web::sign-in::login"
        }
      }
    },
    {
      "text": "The Visitor follows the emailed link and continues",
      "kind": "actor",
      "actor": "visitor",
      "entities": [
        {
          "entity": "sign-in-link",
          "effect": "reads",
          "facts": [
            "Kind"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "instance-web::sign-in::sign-in-link"
        }
      }
    },
    {
      "text": "The Product marks the sign-in link used and signs the member in for 30 days",
      "kind": "product",
      "actor": "visitor",
      "entities": [
        {
          "entity": "sign-in-link",
          "effect": "changes",
          "from": "Active",
          "to": "Used",
          "facts": []
        },
        {
          "entity": "member-account",
          "effect": "changes",
          "facts": [
            "Last active"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "instance-web::sign-in::sign-in-link"
        }
      }
    }
  ]
}
---

# Sign in with a verification check

## Trigger

A member signs in to an instance whose operator turned on sign-in verification.

## Outcome

The member is signed in; a request without a passed check is refused and sends nothing.
