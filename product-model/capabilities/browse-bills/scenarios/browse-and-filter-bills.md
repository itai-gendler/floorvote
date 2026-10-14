---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Standard member opens the Bills page and chooses filters",
      "kind": "actor",
      "actor": "standard-member",
      "entities": [
        {
          "entity": "bill",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "web": {
          "place": "instance-web::workspace::bills"
        }
      }
    },
    {
      "text": "The Product lists the matching bills, tracked bills ahead of untracked ones, with the team's votes, position and the member's own vote on each",
      "kind": "product",
      "actor": "standard-member",
      "entities": [
        {
          "entity": "bill",
          "effect": "reads",
          "facts": [
            "Bill number",
            "Title",
            "State",
            "Session",
            "Status",
            "Stage",
            "Summary",
            "Tags",
            "Relevance score",
            "Priority",
            "Official position",
            "Custom field values",
            "Vote tally"
          ]
        },
        {
          "entity": "member-vote",
          "effect": "reads",
          "facts": [
            "Position"
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

# Browse and filter bills

## Trigger

A member wants to find the bills that matter to a question or a meeting.

## Outcome

The member sees the bills matching their filters, 50 to a page by default.

## Edge cases

- Filters cover state, session year, stage, status, tag, subject, priority, official position, relevance and each custom field; filter groups combine with all or any.
- Search covers bill numbers, titles, abstracts and AI summaries.
- My bills narrows the list to bills the member voted on, commented on or wrote a note on; Not voted narrows it to bills the member has not voted on.
- More than the allowed number of subject filters is refused.
