---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Admin changes the draft's details on its page and saves",
      "kind": "actor",
      "actor": "admin",
      "entities": [
        {
          "entity": "bill",
          "effect": "reads",
          "facts": [
            "Bill number",
            "Title",
            "Summary",
            "Draft text"
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
      "text": "The Product saves the draft, checking that its number stays unique in its state and year",
      "kind": "product",
      "actor": "admin",
      "entities": [
        {
          "entity": "bill",
          "effect": "changes",
          "from": "Draft",
          "to": "Draft",
          "facts": [
            "Bill number",
            "Title",
            "State",
            "Session",
            "Sponsors",
            "Summary",
            "Draft text"
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

# Edit a draft bill

## Trigger

A draft gets its number or title.

## Outcome

The draft shows the new details everywhere; a blank title makes it an untitled draft.

## Edge cases

- A number another bill of the same state and year has is refused.
- Clearing the state is refused.
