---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The central service delivers changes to a bill the instance tracks",
      "kind": "condition",
      "unattended": true,
      "entities": [
        {
          "entity": "bill",
          "effect": "reads",
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
      "text": "The Product updates the bill's legislative data, and has the AI analyze it again when its text changed",
      "kind": "product",
      "entities": [
        {
          "entity": "bill",
          "effect": "changes",
          "facts": [
            "Status",
            "Stage",
            "Last action",
            "History",
            "Committee",
            "Texts",
            "Sponsors",
            "Subjects",
            "Summary",
            "Tags",
            "Relevance score",
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

# Update a tracked bill

## Trigger

A tracked bill moves through the legislature.

## Outcome

The bill shows its new status and text, and the feed records the update; the default feed shows it when the bill has a priority or a member acted on it that day.

## Edge cases

- A bill added by hand keeps being analyzed when its text changes, whether or not it matches the keywords.
- An update never turns a bill added by hand back into an untracked one.
