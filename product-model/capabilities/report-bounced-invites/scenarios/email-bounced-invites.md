---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The hourly check finds new bounces of emails sent to pending invites",
      "kind": "condition",
      "unattended": true,
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
      "text": "The Product marks each such pending invite as bounced, with the receiving server's reason",
      "kind": "product",
      "entities": [
        {
          "entity": "member-account",
          "effect": "changes",
          "from": "Pending invite",
          "to": "Pending invite",
          "facts": [
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
      "text": "The Product emails each bounced address to the member who sent the invite, or to every active owner when that member is no longer an active admin",
      "kind": "product",
      "entities": [
        {
          "entity": "member-account",
          "effect": "reads",
          "facts": [
            "Invited by"
          ]
        },
        {
          "entity": "admin",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "owner",
          "effect": "reads",
          "facts": []
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

# Report bounced invites

## Trigger

An invite or sign-in email to someone who has not signed in yet bounces.

## Outcome

The Members page shows "Email bounced" on the invite, and an admin or owner has an email linking to it with advice to correct the address.

## Edge cases

- A bounce is reported once; a failed notification email is not retried.
- A later successful delivery to the address clears it as previously bounced.
