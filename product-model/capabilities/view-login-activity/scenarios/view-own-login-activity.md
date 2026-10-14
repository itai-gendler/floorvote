---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Standard member opens their login activity on their account page",
      "kind": "actor",
      "actor": "standard-member",
      "entities": [
        {
          "entity": "login-activity",
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
      "text": "The Product lists the member's 50 most recent login activity entries",
      "kind": "product",
      "actor": "standard-member",
      "entities": [
        {
          "entity": "login-activity",
          "effect": "reads",
          "facts": [
            "Event",
            "Link kind",
            "Changed by",
            "Country",
            "When"
          ]
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

# View your own login activity

## Trigger

A member wants to check when and from where their account was used.

## Outcome

The member sees their recent sign-in requests, sign-ins and sign-outs.
