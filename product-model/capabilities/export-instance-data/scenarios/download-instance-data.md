---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Admin picks CSV or JSON and starts the export",
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
      "text": "The Product assembles the instance data page by page and downloads it, showing progress",
      "kind": "product",
      "actor": "admin",
      "entities": [
        {
          "entity": "bill",
          "effect": "reads",
          "facts": [
            "Bill number",
            "Title",
            "Status",
            "Summary",
            "Tags",
            "Priority",
            "Official position",
            "Custom field values"
          ]
        },
        {
          "entity": "custom-event",
          "effect": "reads",
          "facts": [
            "Title",
            "Date"
          ]
        },
        {
          "entity": "custom-field",
          "effect": "reads",
          "facts": [
            "Name",
            "Type"
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

# Download the instance data

## Trigger

The organization wants its data for a report, an archive or another tool.

## Outcome

The admin has the instance data on their computer.

## Edge cases

- Legislature subjects an operator has suppressed for a state stay out of the export.
