---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Admin enters the corrected address for a pending invite",
      "kind": "actor",
      "actor": "admin",
      "entities": [
        {
          "entity": "member-account",
          "effect": "reads",
          "facts": [
            "Email",
            "Email bounced"
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
      "text": "The Product changes the address, stops every unused link sent to the old one and emails an invite to the new one",
      "kind": "product",
      "actor": "admin",
      "entities": [
        {
          "entity": "member-account",
          "effect": "changes",
          "from": "Pending invite",
          "to": "Pending invite",
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
          "place": "instance-web::settings::members"
        }
      }
    }
  ]
}
---

# Correct a pending invite's address

## Trigger

An invite bounced because the address had a typo.

## Outcome

The pending invite has the corrected address and a new invite; the change shows in the member's login activity.

## Edge cases

- The same address, an address another member uses, an invalid address or one that bounced before is refused.
- A member who has signed in, a deactivated member, or the admin's own account cannot be changed this way.
