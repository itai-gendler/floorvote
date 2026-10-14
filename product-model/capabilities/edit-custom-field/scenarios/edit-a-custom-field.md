---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Admin changes a custom field and saves",
      "kind": "actor",
      "actor": "admin",
      "entities": [
        {
          "entity": "custom-field",
          "effect": "reads",
          "facts": [
            "Name",
            "Type",
            "Options",
            "Multiple",
            "Pinned"
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
      "text": "The Product saves the custom field",
      "kind": "product",
      "actor": "admin",
      "entities": [
        {
          "entity": "custom-field",
          "effect": "changes",
          "facts": [
            "Name",
            "Options",
            "Multiple",
            "Pinned"
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

# Edit a custom field

## Trigger

A field needs another option or a clearer name.

## Outcome

Bills show the updated custom field.

## Edge cases

- Options and multiple values apply only to dropdowns.
- Turning off multiple values is refused while any bill holds several, and the refusal lists those bills.
