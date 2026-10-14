---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Standard member edits one of their comments and saves it",
      "kind": "actor",
      "actor": "standard-member",
      "entities": [
        {
          "entity": "comment",
          "effect": "reads",
          "facts": [
            "Content"
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
      "text": "The Product saves the new text, updates its feed preview and notifies only mentions the edit added",
      "kind": "product",
      "actor": "standard-member",
      "entities": [
        {
          "entity": "comment",
          "effect": "changes",
          "facts": [
            "Content",
            "Mentions"
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

# Edit your comment

## Trigger

A member fixes a typo or adds a point.

## Outcome

The comment shows the new text everywhere; nobody already notified is notified again.

## Edge cases

- Editing someone else's comment is refused, for admins too.
