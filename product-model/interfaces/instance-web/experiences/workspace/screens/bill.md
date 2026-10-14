---
{
  "entities": [
    {
      "entity": "bill",
      "shows": [
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
        "New match",
        "Vote tally",
        "Draft text"
      ],
      "collects": [
        "Priority",
        "Official position",
        "Custom field values",
        "Title",
        "Bill number",
        "Summary",
        "Draft text"
      ]
    },
    {
      "entity": "member-vote",
      "shows": [
        "Position",
        "Voted at"
      ],
      "collects": [
        "Position"
      ]
    },
    {
      "entity": "comment",
      "shows": [
        "Content",
        "Posted at"
      ],
      "collects": [
        "Content"
      ]
    },
    {
      "entity": "reaction",
      "shows": [
        "Emoji"
      ],
      "collects": [
        "Emoji"
      ]
    },
    {
      "entity": "personal-note",
      "shows": [
        "Content"
      ],
      "collects": [
        "Content"
      ]
    },
    {
      "entity": "calendar-entry",
      "shows": [
        "Kind",
        "Date",
        "Time",
        "Location",
        "Description"
      ]
    },
    {
      "entity": "custom-field",
      "shows": [
        "Name",
        "Type",
        "Options",
        "Pinned"
      ]
    },
    {
      "entity": "role",
      "shows": [
        "Name"
      ]
    }
  ],
  "entryPoints": [
    {
      "instance-web": "/bills/:billId"
    },
    {
      "instance-web": "/:state/:session/:billNumber"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/pages/BillDetail.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/routes/billsApi/detail.ts"
    }
  ]
}
---

# Bill

One bill: its legislative data and text, the AI summary, tags and relevance, the team's votes, official position, custom fields and comments, the member's own vote and note, and its upcoming dates. A draft bill's page also edits, links or deletes the draft.
