---
{
  "kind": "alternative",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Standard member picks a saved view in the switcher or opens its bookmarked link",
      "kind": "actor",
      "actor": "standard-member",
      "entities": [
        {
          "entity": "saved-view",
          "effect": "reads",
          "facts": [
            "Name"
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
      "text": "The Product applies the saved view's filters to the bill list",
      "kind": "product",
      "actor": "standard-member",
      "entities": [
        {
          "entity": "saved-view",
          "effect": "reads",
          "facts": [
            "Filters"
          ]
        },
        {
          "entity": "bill",
          "effect": "reads",
          "facts": [
            "Bill number",
            "Title",
            "Status",
            "Priority"
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

# Switch to a saved view

## Trigger

A member returns to a filter combination the team set up, such as a committee's bills.

## Outcome

The list shows the saved view's bills; a link with the view's previous name still opens it.
