---
{
  "kind": "validation",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Admin creates a draft with a number already used in the same state and year",
      "kind": "actor",
      "actor": "admin",
      "entities": [],
      "contexts": {
        "web": {
          "place": "instance-web::settings::draft-bills"
        }
      }
    },
    {
      "text": "Another bill holds that number in that state and year",
      "kind": "condition",
      "actor": "admin",
      "entities": [
        {
          "entity": "bill",
          "effect": "reads",
          "facts": [
            "Bill number",
            "State",
            "Session"
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
      "text": "The Product refuses and names the conflict",
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

# Create a draft with a number already used

## Trigger

An admin reuses a number by mistake.

## Outcome

No draft is created; a custom field value that does not fit its field is refused the same way, before anything is written.
