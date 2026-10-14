---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Admin chooses to re-analyze everything tracked or only what is prioritized",
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
      "text": "The Product queues the chosen bills for a fresh AI analysis",
      "kind": "product",
      "actor": "admin",
      "entities": [
        {
          "entity": "bill",
          "effect": "changes",
          "facts": [
            "Analysis"
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

# Re-analyze tracked bills

## Trigger

The AI instructions changed and existing summaries should follow them.

## Outcome

Each queued bill gets a new summary, tags and relevance score as analysis runs; in a demo nothing is analyzed.
