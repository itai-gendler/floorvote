---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Admin edits the keyword list and sees live counts of what it matches and would newly match or unmatch",
      "kind": "actor",
      "actor": "admin",
      "entities": [
        {
          "entity": "instance-settings",
          "effect": "reads",
          "facts": [
            "Keywords"
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
      "text": "The Admin confirms the summary of what will be analyzed, downgraded or kept, and saves",
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
      "text": "The Product saves the keywords and registers them for the instance's covered states, so filings that arrive later match against them",
      "kind": "product",
      "actor": "admin",
      "entities": [
        {
          "entity": "instance-settings",
          "effect": "changes",
          "facts": [
            "Keywords"
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
      "text": "The Product starts tracking and analyzing the bills it holds that now match",
      "kind": "product",
      "actor": "admin",
      "entities": [
        {
          "entity": "bill",
          "effect": "changes",
          "as": "newly-matched",
          "from": "Untracked",
          "to": "Matched",
          "facts": []
        }
      ],
      "contexts": {
        "web": {
          "place": "instance-web::settings::config"
        }
      }
    },
    {
      "text": "The Product stops tracking keyword matches that no longer match and that nobody engaged with or prioritized",
      "kind": "product",
      "actor": "admin",
      "entities": [
        {
          "entity": "bill",
          "effect": "changes",
          "as": "unmatched",
          "from": "Matched",
          "to": "Untracked",
          "facts": []
        }
      ],
      "contexts": {
        "web": {
          "place": "instance-web::settings::config"
        }
      }
    },
    {
      "text": "The Product keeps tracking, as added by hand, keyword matches that no longer match but carry votes, a position, discussion, notes or a priority",
      "kind": "product",
      "actor": "admin",
      "entities": [
        {
          "entity": "bill",
          "effect": "changes",
          "as": "engaged",
          "from": "Matched",
          "to": "Added",
          "facts": []
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

# Save new keywords

## Trigger

The team's issues change, or the keywords catch too much or too little.

## Outcome

The instance tracks the bills the new keywords match, has kept every bill the team engaged with, and reports how many bills were queued, downgraded and kept.

## Edge cases

- Saving an empty list tracks no new bills and downgrades nothing.
- A list of just * matches every bill, and saving it queues every unanalyzed bill for analysis.
- If the central service cannot be reached or asks to wait, the keywords are still saved and the report says the central half did not run.
