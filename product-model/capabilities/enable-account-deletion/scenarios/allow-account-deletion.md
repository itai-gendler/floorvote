---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Owner turns account deletion on",
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
      "text": "The Product allows permanent account deletion",
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

# Allow account deletion

## Trigger

The organization honours requests to erase people's data.

## Outcome

Delete actions appear for admins and on members' own account pages.
