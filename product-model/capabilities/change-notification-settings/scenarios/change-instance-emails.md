---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Admin turns conversation emails, the digest or the week-ahead email on or off, or changes their cadence and day",
      "kind": "actor",
      "actor": "admin",
      "entities": [
        {
          "entity": "instance-settings",
          "effect": "reads",
          "facts": [
            "Conversation emails",
            "Email digest",
            "Week-ahead email"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "instance-web::settings::notification-settings"
        }
      }
    },
    {
      "text": "The Product saves each change as it is made",
      "kind": "product",
      "actor": "admin",
      "entities": [
        {
          "entity": "instance-settings",
          "effect": "changes",
          "facts": [
            "Conversation emails",
            "Email digest",
            "Week-ahead email"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "instance-web::settings::notification-settings"
        }
      }
    }
  ]
}
---

# Change the instance's emails

## Trigger

The team wants more, fewer or differently timed emails.

## Outcome

Emails follow the new settings from their next run; in-app notifications are unaffected.
