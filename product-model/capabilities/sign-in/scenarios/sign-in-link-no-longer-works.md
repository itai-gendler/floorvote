---
{
  "kind": "validation",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Visitor follows a sign-in link that was already used or has expired",
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
      "text": "The sign-in link is used or past its expiry",
      "kind": "condition",
      "actor": "visitor",
      "entities": [
        {
          "entity": "sign-in-link",
          "effect": "reads",
          "facts": [
            "Expires"
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
      "text": "The Product says the link no longer works and offers to send a new one",
      "kind": "product",
      "actor": "visitor",
      "entities": [],
      "contexts": {
        "web": {
          "place": "instance-web::sign-in::sign-in-link"
        }
      }
    }
  ]
}
---

# Follow a used or expired link

## Trigger

A person opens an old sign-in link or invite.

## Outcome

Nobody is signed in, and the person can ask for a new link.
