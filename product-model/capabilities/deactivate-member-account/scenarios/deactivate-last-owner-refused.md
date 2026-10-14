---
{
  "kind": "validation",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Owner tries to deactivate the only active owner",
      "kind": "actor",
      "actor": "owner",
      "entities": [
        {
          "entity": "member-account",
          "effect": "reads",
          "facts": [
            "Permission level"
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
      "text": "The Product refuses: the last owner cannot be deactivated",
      "kind": "product",
      "actor": "owner",
      "entities": [],
      "contexts": {
        "web": {
          "place": "instance-web::settings::members"
        }
      }
    }
  ]
}
---

# Deactivate the last owner

## Trigger

An owner tries to remove the instance's last owner.

## Outcome

The owner stays active.
