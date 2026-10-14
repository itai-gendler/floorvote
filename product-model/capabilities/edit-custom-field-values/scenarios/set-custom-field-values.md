---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Admin fills in or clears custom fields on a bill",
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
          "place": "instance-web::workspace::bill"
        }
      }
    },
    {
      "text": "The Product checks each value against its custom field and saves it with the admin as the one who set it",
      "kind": "product",
      "actor": "admin",
      "entities": [
        {
          "entity": "bill",
          "effect": "changes",
          "facts": [
            "Custom field values"
          ]
        },
        {
          "entity": "custom-field",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "web": {
          "place": "instance-web::workspace::bill"
        }
      }
    }
  ]
}
---

# Fill in custom fields

## Trigger

An admin records something the team tracks, such as who leads on the bill.

## Outcome

The bill shows the values, and the Bills page can filter on them.

## Edge cases

- A value that does not fit its custom field — an option a dropdown does not offer, or a malformed date — is refused, and nothing is saved.
