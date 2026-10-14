---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Standard member writes or changes their note on a bill",
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
      "text": "The Product saves the member's one personal note on the bill",
      "kind": "product",
      "actor": "standard-member",
      "entities": [
        {
          "entity": "personal-note",
          "effect": "creates",
          "facts": [
            "Content",
            "Updated at"
          ]
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

# Write a personal note

## Trigger

A member wants to remember something about a bill for themselves.

## Outcome

The note is there next time the member opens the bill, and the bill joins their My bills list while the note has text.

## Edge cases

- A note over 50 KB is refused.
- Saving changes the existing note rather than adding another.
