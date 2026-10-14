---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Admin renames a saved view or saves new filters into it",
      "kind": "actor",
      "actor": "admin",
      "entities": [
        {
          "entity": "saved-view",
          "effect": "reads",
          "facts": [
            "Name",
            "Filters"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "instance-web::workspace::bills"
        }
      }
    },
    {
      "text": "The Product saves the change, and a rename gives the saved view a new link name while keeping the previous one working",
      "kind": "product",
      "actor": "admin",
      "entities": [
        {
          "entity": "saved-view",
          "effect": "changes",
          "facts": [
            "Name",
            "Filters",
            "Link name"
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

# Rename or update a saved view

## Trigger

A committee is renamed or its bills need different filters.

## Outcome

Members see the updated saved view; bookmarks to its previous name still open it.
