---
{
  "kind": "edge",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The AI cannot analyze a tracked bill: the service is unavailable, or the bill has no full text yet",
      "kind": "condition",
      "unattended": true,
      "entities": [
        {
          "entity": "bill",
          "effect": "reads",
          "facts": [
            "Texts"
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
      "text": "The Product keeps the bill without a summary and records that analysis is pending",
      "kind": "product",
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
          "place": "instance-web::workspace::bill"
        }
      }
    },
    {
      "text": "Every hour the Product queues bills whose analysis stalled again, up to five attempts each",
      "kind": "product",
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
          "place": "instance-web::workspace::bill"
        }
      }
    }
  ]
}
---

# Analysis is unavailable

## Trigger

The AI provider is overloaded or out of credit, or the legislature has not published text.

## Outcome

Members see that the bill is not analyzed yet; a bill whose text the AI can never process says so, and is analyzed again only when its text changes.
