---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Owner turns account deletion off",
      "kind": "actor",
      "actor": "owner",
      "entities": [
        {
          "entity": "instance-settings",
          "effect": "reads",
          "facts": [
            "Account deletion"
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
      "text": "The Product stops permanent account deletion",
      "kind": "product",
      "actor": "owner",
      "entities": [
        {
          "entity": "instance-settings",
          "effect": "changes",
          "facts": [
            "Account deletion"
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

# Turn account deletion off

## Trigger

The organization wants departed members' engagement kept.

## Outcome

Accounts can only be deactivated, which hides their activity until reactivation.
