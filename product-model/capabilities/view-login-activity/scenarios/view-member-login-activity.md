---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Admin opens a member's login activity on the Members page",
      "kind": "actor",
      "actor": "admin",
      "entities": [
        {
          "entity": "member-account",
          "effect": "reads",
          "facts": [
            "Email"
          ]
        },
        {
          "entity": "login-activity",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "web": {
          "place": "instance-web::settings::members"
        }
      }
    },
    {
      "text": "The Product lists the member's recent login activity with each emailed link's delivery status, and whether the email provider refuses to send to the address",
      "kind": "product",
      "actor": "admin",
      "entities": [
        {
          "entity": "login-activity",
          "effect": "reads",
          "facts": [
            "Event",
            "Link kind",
            "Changed by",
            "Country",
            "Device",
            "When"
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

# View a member's login activity

## Trigger

A member reports that sign-in links are not arriving, or the Members page flags login trouble.

## Outcome

The admin sees what happened to the member's recent sign-ins and emails.

## Edge cases

- The Members page flags login trouble for a member who asked for two or more sign-in links in the last 14 days without signing in since.
- Admins can also list the last 100 sign-in attempts from addresses no member has.
- When the email provider cannot be asked, the list still shows without delivery details.
