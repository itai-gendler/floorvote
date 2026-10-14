---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Admin chooses to refresh legislative data and confirms",
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
      "text": "The Product queues every bill it holds for a refresh of its legislative data without analysis",
      "kind": "product",
      "actor": "admin",
      "entities": [
        {
          "entity": "bill",
          "effect": "changes",
          "facts": [
            "Status",
            "Stage",
            "Sponsors",
            "Last action",
            "History",
            "Subjects"
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

# Refresh every bill's data

## Trigger

Bill details look out of date.

## Outcome

The bills show the central service's current data; summaries stay as they were.
