---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The central service delivers a new filing from a covered state that the keywords do not match",
      "kind": "condition",
      "unattended": true,
      "entities": [
        {
          "entity": "instance-settings",
          "effect": "reads",
          "facts": [
            "Covered states",
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
      "text": "The Product adds the bill with its legislative data and no analysis",
      "kind": "product",
      "entities": [
        {
          "entity": "bill",
          "effect": "creates",
          "to": "Untracked",
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
            "Subjects"
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

# Receive a bill to browse

## Trigger

A bill is introduced or changes in a covered state.

## Outcome

Members can find the bill on the Bills page, after the tracked bills.
