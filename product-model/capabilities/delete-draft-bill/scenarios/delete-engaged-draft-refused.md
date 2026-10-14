---
{
  "kind": "validation",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Admin tries to delete a draft",
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
      "text": "The draft has votes, a position, discussion or notes",
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
      "text": "The Product refuses and says to link the draft instead",
      "kind": "product",
      "actor": "admin",
      "entities": [],
      "contexts": {
        "web": {
          "place": "instance-web::settings::draft-bills"
        }
      }
    }
  ]
}
---

# Delete a draft with engagement

## Trigger

An admin tries to delete a draft the team discussed.

## Outcome

The draft and its engagement stay; a filed bill can never be deleted.
