---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Admin enters a number for the draft and creates it",
      "kind": "actor",
      "actor": "admin",
      "entities": [],
      "contexts": {
        "web": {
          "place": "instance-web::settings::draft-bills"
        }
      },
      "capability": "create-draft-bill"
    },
    {
      "text": "The Product creates the draft and opens its page",
      "kind": "product",
      "actor": "admin",
      "entities": [
        {
          "entity": "bill",
          "effect": "creates",
          "to": "Draft",
          "facts": [
            "Bill number",
            "Title",
            "State",
            "Session"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "instance-web::settings::draft-bills"
        }
      },
      "capability": "create-draft-bill"
    },
    {
      "text": "The Admin adds the draft's title and summary on its page and saves",
      "kind": "actor",
      "actor": "admin",
      "entities": [
        {
          "entity": "bill",
          "effect": "reads",
          "facts": [
            "Bill number",
            "Title",
            "Summary"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "instance-web::workspace::bill"
        }
      },
      "capability": "edit-draft-bill"
    },
    {
      "text": "The Product saves the draft",
      "kind": "product",
      "actor": "admin",
      "entities": [
        {
          "entity": "bill",
          "effect": "changes",
          "from": "Draft",
          "to": "Draft",
          "facts": [
            "Title",
            "Summary"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "instance-web::workspace::bill"
        }
      },
      "capability": "edit-draft-bill"
    }
  ]
}
---

# Create a draft and fill it in

## Trigger

A bill request is circulating before it is introduced.

## Outcome

The admin is on the draft's page with its details saved, ready for the team's votes and comments.
