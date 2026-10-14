---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Admin deletes a custom field",
      "kind": "actor",
      "actor": "admin",
      "entities": [
        {
          "entity": "custom-field",
          "effect": "reads",
          "facts": [
            "Name"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "instance-web::settings::config"
        }
      }
    },
    {
      "text": "The Product removes the custom field and its value on every bill",
      "kind": "product",
      "actor": "admin",
      "entities": [
        {
          "entity": "custom-field",
          "effect": "removes"
        },
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
          "place": "instance-web::settings::config"
        }
      }
    }
  ]
}
---

# Delete a custom field

## Trigger

The team stops tracking something.

## Outcome

The custom field and all its values are gone.
