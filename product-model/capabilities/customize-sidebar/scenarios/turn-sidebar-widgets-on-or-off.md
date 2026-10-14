---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Admin turns a sidebar widget on or off",
      "kind": "actor",
      "actor": "admin",
      "entities": [
        {
          "entity": "instance-settings",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "web": {
          "place": "instance-web::workspace"
        }
      }
    },
    {
      "text": "The Product saves the choice and every member's sidebar follows it",
      "kind": "product",
      "actor": "admin",
      "entities": [
        {
          "entity": "instance-settings",
          "effect": "changes",
          "facts": [
            "Sidebar widgets"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "instance-web::workspace"
        }
      }
    }
  ]
}
---

# Turn sidebar widgets on or off

## Trigger

An admin wants members reminded of prioritized bills to vote on, or of upcoming hearings.

## Outcome

Every member's sidebar shows the widgets that are on; a widget shows only while it has something to list.
