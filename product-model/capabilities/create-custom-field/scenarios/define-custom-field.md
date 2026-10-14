---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Admin names a field, picks its type and, for a dropdown, its options",
      "kind": "actor",
      "actor": "admin",
      "entities": [],
      "contexts": {
        "web": {
          "place": "instance-web::settings::config"
        }
      }
    },
    {
      "text": "The Product adds the custom field after the existing ones",
      "kind": "product",
      "actor": "admin",
      "entities": [
        {
          "entity": "custom-field",
          "effect": "creates",
          "facts": [
            "Name",
            "Type",
            "Options",
            "Multiple",
            "Order",
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

# Define a custom field

## Trigger

The team tracks something about bills that FloorVote does not.

## Outcome

The custom field appears on every bill page and as a filter on the Bills page.

## Edge cases

- A field without a name, of an unknown type, or a dropdown without options is refused.
