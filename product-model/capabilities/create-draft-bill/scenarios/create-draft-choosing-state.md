---
{
  "kind": "alternative",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Admin enters what is known about the draft and chooses which covered state it belongs to",
      "kind": "actor",
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
      "text": "The Product creates the draft in the chosen state, numbering it when no number was given, and records it as added in the feed",
      "kind": "product",
      "actor": "admin",
      "entities": [
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

# Create a draft bill choosing its state

## Trigger

An instance covering several states starts tracking a draft.

## Outcome

The draft exists in its state with an address on that state's bills.

## Edge cases

- Leaving the state out is refused, since a draft without a state cannot have an address.
