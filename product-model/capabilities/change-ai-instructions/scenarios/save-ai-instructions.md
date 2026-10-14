---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Admin edits the AI context, the relevance question or the tag taxonomy and saves",
      "kind": "actor",
      "actor": "admin",
      "entities": [
        {
          "entity": "instance-settings",
          "effect": "reads",
          "facts": [
            "AI context",
            "Relevance question",
            "Tag taxonomy"
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
      "text": "The Product saves the instructions, which apply to every analysis from then on",
      "kind": "product",
      "actor": "admin",
      "entities": [
        {
          "entity": "instance-settings",
          "effect": "changes",
          "facts": [
            "AI context",
            "Relevance question",
            "Tag taxonomy"
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

# Save AI instructions

## Trigger

The team wants summaries, scores or tags that fit its work better.

## Outcome

New analyses follow the new instructions; the admin is offered to re-analyze tracked bills.

## Edge cases

- The AI may only apply tags from the taxonomy; any other tag it proposes is dropped.
