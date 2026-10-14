---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Visitor enters their email address and asks to be emailed a link",
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
      "text": "The Product creates a sign-in link for the matching member account and emails it, valid for 60 minutes",
      "kind": "product",
      "actor": "visitor",
      "entities": [
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

# Sign in with an emailed link

## Trigger

A member wants to use the instance and is not signed in, on an instance without sign-in verification.

## Outcome

The member is signed in; using the instance keeps the session alive for another 30 days each time.

## Edge cases

- The page always answers "Check your email for a sign-in link", whether or not the address belongs to a member.
- A member who already holds five unused, unexpired sign-in links gets the same answer and no new link.
- Too many requests from one connection are refused for a moment.
- Following a link that is still valid while already signed in asks before switching accounts.
