---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Standard member opens a bill from the list, the feed, the calendar or a link",
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
          "place": "instance-web::workspace::bill"
        }
      }
    },
    {
      "text": "The Product shows the bill with its summary, text versions, history, the team's vote tally and official position, the first comments, and the member's own vote and note",
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
            "Abstract",
            "Sponsors",
            "Last action",
            "History",
            "Committee",
            "Texts",
            "Roll-call votes",
            "Subjects",
            "Provider details",
            "Summary",
            "Tags",
            "Relevance score",
            "Analysis",
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
        },
        {
          "entity": "comment",
          "effect": "reads",
          "facts": [
            "Content",
            "Posted at"
          ]
        },
        {
          "entity": "personal-note",
          "effect": "reads",
          "facts": [
            "Content"
          ]
        },
        {
          "entity": "calendar-entry",
          "effect": "reads",
          "facts": [
            "Kind",
            "Date",
            "Time",
            "Location",
            "Description"
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
      "text": "The Product marks the member's notifications about this bill read",
      "kind": "product",
      "actor": "standard-member",
      "entities": [
        {
          "entity": "notification",
          "effect": "changes",
          "from": "Unread",
          "to": "Read",
          "facts": []
        },
        {
          "entity": "bill",
          "effect": "reads",
          "facts": []
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

# Read a bill

## Trigger

A member wants to understand a bill and where the team stands on it.

## Outcome

The member sees the bill and the team's engagement with it; the tally counts only active members whose voting is allowed.

## Edge cases

- A bill whose text has not been analyzed yet, or could not be, says so instead of showing a summary.
- Opening a text version shows that version of the bill's text.
- Bills are addressed by state, session and number; an address that matches no bill shows a not-found page.
