---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The central service delivers a filing whose title, description or number matches a keyword, with its full text",
      "kind": "condition",
      "unattended": true,
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
          "place": "instance-web::workspace::bills"
        }
      }
    },
    {
      "text": "The Product has the AI read the filing's text with the instance's AI context, relevance question and tag taxonomy",
      "kind": "product",
      "entities": [
        {
          "entity": "instance-settings",
          "effect": "reads",
          "facts": [
            "AI context",
            "Relevance question",
            "Tag taxonomy",
            "Name"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "instance-web::workspace::bills"
        }
      }
    },
    {
      "text": "The Product keeps the bill as a keyword match with its summary, taxonomy tags and relevance score, and records it as a new match once",
      "kind": "product",
      "entities": [
        {
          "entity": "bill",
          "effect": "creates",
          "to": "Matched",
          "facts": [
            "Bill number",
            "Title",
            "State",
            "Session",
            "Status",
            "Stage",
            "Abstract",
            "Sponsors",
            "Last action",
            "History",
            "Committee",
            "Texts",
            "Subjects",
            "Summary",
            "Tags",
            "Relevance score",
            "Analysis",
            "New match"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "instance-web::workspace::bills"
        }
      }
    }
  ]
}
---

# Analyze a new keyword match

## Trigger

A bill relevant to the team's keywords appears.

## Outcome

The bill is tracked, waits in New matches when its relevance reaches the threshold, and the feed records "New bill matching your keywords" once.

## Edge cases

- A bill already analyzed against the same text is not analyzed again.
- A bill that was untracked becomes a keyword match the same way once it matches.
- A demo instance never runs the AI.
