---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Admin sets the minimum relevance for new matches and saves",
      "kind": "actor",
      "actor": "admin",
      "entities": [
        {
          "entity": "instance-settings",
          "effect": "reads",
          "facts": [
            "New match minimum relevance"
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
      "text": "The Product saves the threshold, treating anything invalid or negative as 0",
      "kind": "product",
      "actor": "admin",
      "entities": [
        {
          "entity": "instance-settings",
          "effect": "changes",
          "facts": [
            "New match minimum relevance"
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

# Set the new match threshold

## Trigger

Too many low-relevance matches crowd the worklist.

## Outcome

New matches and the admin digest show only matches at or above the threshold; the feed still records every match.
