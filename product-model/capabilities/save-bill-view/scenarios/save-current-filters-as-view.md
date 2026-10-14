---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Admin gives the current filters a name and saves them for the team",
      "kind": "actor",
      "actor": "admin",
      "entities": [],
      "contexts": {
        "web": {
          "place": "instance-web::workspace::bills"
        }
      }
    },
    {
      "text": "The Product saves the saved view at the end of the switcher with a link name made from its name",
      "kind": "product",
      "actor": "admin",
      "entities": [
        {
          "entity": "saved-view",
          "effect": "creates",
          "facts": [
            "Name",
            "Filters",
            "Link name",
            "Order"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "instance-web::workspace::bills"
        }
      }
    }
  ]
}
---

# Save the current filters as a view

## Trigger

An admin wants a filter combination to be a permanent part of the team's setup.

## Outcome

Every member can switch to the saved view and bookmark its link.

## Edge cases

- A saved view outlives the admin who made it.
