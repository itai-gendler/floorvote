---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Admin enters what is known — number, title, year, sponsor, summary, text and custom fields — and creates the draft",
      "kind": "actor",
      "actor": "admin",
      "entities": [
        {
          "entity": "custom-field",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "web": {
          "place": "instance-web::settings::draft-bills"
        }
      }
    },
    {
      "text": "The Product creates the draft in the instance's state, numbering it when no number was given, and records it as added in the feed",
      "kind": "product",
      "actor": "admin",
      "entities": [
        {
          "entity": "instance-settings",
          "effect": "reads",
          "facts": [
            "Covered states"
          ]
        },
        {
          "entity": "bill",
          "effect": "creates",
          "to": "Draft",
          "facts": [
            "Bill number",
            "Title",
            "State",
            "Session",
            "Sponsors",
            "Summary",
            "Draft text",
            "Custom field values"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "instance-web::settings::draft-bills"
        }
      }
    },
    {
      "text": "The Product opens the new draft's page",
      "kind": "product",
      "actor": "admin",
      "entities": [
        {
          "entity": "bill",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "web": {
          "place": "instance-web::settings::draft-bills"
        }
      }
    }
  ]
}
---

# Create a draft bill

## Trigger

A bill request is circulating months before it is introduced.

## Outcome

The team can vote, comment, keep notes and set a position on the draft as on any bill.

## Edge cases

- If the central service cannot say which session is current, the year defaults to the newest year among the instance's filed bills in that state.
