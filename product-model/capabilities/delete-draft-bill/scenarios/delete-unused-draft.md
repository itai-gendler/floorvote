---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Admin deletes a draft from the Draft bills page",
      "kind": "actor",
      "actor": "admin",
      "entities": [
        {
          "entity": "bill",
          "effect": "reads",
          "facts": [
            "Bill number",
            "Title"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "instance-web::settings::draft-bills"
        }
      }
    },
    {
      "text": "Nobody has voted, set a position, commented or written a note on the draft",
      "kind": "condition",
      "actor": "admin",
      "entities": [
        {
          "entity": "bill",
          "effect": "reads",
          "facts": [
            "Official position"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "instance-web::settings::draft-bills"
        }
      }
    },
    {
      "text": "The Product removes the draft and its links to calendar events",
      "kind": "product",
      "actor": "admin",
      "entities": [
        {
          "entity": "bill",
          "effect": "removes",
          "from": "Draft"
        }
      ],
      "contexts": {
        "web": {
          "place": "instance-web::settings::draft-bills"
        }
      }
    }
  ]
}
---

# Delete a draft bill

## Trigger

A bill request was dropped.

## Outcome

The draft is gone; calendar events it was linked to stay.
