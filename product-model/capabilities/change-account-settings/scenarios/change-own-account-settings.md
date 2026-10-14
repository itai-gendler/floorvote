---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Standard member changes their name, subtitle or email choices on their account page",
      "kind": "actor",
      "actor": "standard-member",
      "entities": [
        {
          "entity": "member-account",
          "effect": "reads",
          "facts": [
            "Name",
            "Subtitle",
            "Digest emails",
            "Week-ahead emails",
            "Reply emails"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "instance-web::workspace::account"
        }
      }
    },
    {
      "text": "The Product saves only the settings the member changed",
      "kind": "product",
      "actor": "standard-member",
      "entities": [
        {
          "entity": "member-account",
          "effect": "changes",
          "facts": [
            "Name",
            "Subtitle",
            "Digest emails",
            "Week-ahead emails",
            "Reply emails"
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

# Change your account settings

## Trigger

A member wants fewer emails, or a title under their name.

## Outcome

The team sees the new name and subtitle, and the member gets only the emails they chose.

## Edge cases

- A blank name shows the member by email; a name over 100 characters or a subtitle over 200 is refused.
- The account page notes when the organization has turned an email off for everyone.
- Unsubscribe links in emails lead to the matching setting.
