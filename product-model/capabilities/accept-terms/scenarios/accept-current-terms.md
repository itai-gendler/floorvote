---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The member has not accepted terms dated on or after the current legal terms",
      "kind": "condition",
      "actor": "standard-member",
      "entities": [
        {
          "entity": "instance-settings",
          "effect": "reads",
          "facts": [
            "Legal terms"
          ]
        },
        {
          "entity": "member-account",
          "effect": "reads",
          "facts": [
            "Accepted terms"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "instance-web::workspace::terms"
        }
      }
    },
    {
      "text": "The Standard member reads and accepts the terms",
      "kind": "actor",
      "actor": "standard-member",
      "entities": [
        {
          "entity": "instance-settings",
          "effect": "reads",
          "facts": [
            "Legal terms"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "instance-web::workspace::terms"
        }
      }
    },
    {
      "text": "The Product records the acceptance against the current terms date",
      "kind": "product",
      "actor": "standard-member",
      "entities": [
        {
          "entity": "member-account",
          "effect": "changes",
          "facts": [
            "Accepted terms"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "instance-web::workspace::terms"
        }
      }
    }
  ]
}
---

# Accept the current terms

## Trigger

A member signs in after the operator published or updated the legal terms.

## Outcome

The member can use the instance; an earlier acceptance stays on record alongside the new one.

## Edge cases

- There is no decline button; the member can only sign out instead.
