---
{
  "kind": "validation",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Visitor enters an email address that no member account has",
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
      "text": "The Product sends nothing and gives the same answer it gives a member",
      "kind": "product",
      "actor": "visitor",
      "entities": [],
      "contexts": {
        "web": {
          "place": "instance-web::sign-in::login"
        }
      }
    }
  ]
}
---

# Ask for a link with an unknown address

## Trigger

Someone who was never invited tries to sign in.

## Outcome

No account is created and no email is sent; admins can see the attempt among unknown sign-in attempts.
