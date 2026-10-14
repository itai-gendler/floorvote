---
{
  "kind": "alternative",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Admin selects bills on the Bills page and sets, adds or removes custom field values for all of them",
      "kind": "actor",
      "actor": "admin",
      "entities": [
        {
          "entity": "custom-field",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "bill",
          "effect": "reads",
          "facts": [
            "Custom field values"
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
      "text": "The Product applies the values to every selected bill, adding to or removing from multi-value dropdowns without disturbing other values",
      "kind": "product",
      "actor": "admin",
      "entities": [
        {
          "entity": "bill",
          "effect": "changes",
          "facts": [
            "Custom field values"
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

# Fill in custom fields on many bills

## Trigger

An admin tags a package of bills with the same lead person.

## Outcome

Every selected bill has the values.
