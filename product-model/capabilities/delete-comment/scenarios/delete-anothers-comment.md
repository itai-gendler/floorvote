---
{
  "kind": "alternative",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Admin deletes another member's comment",
      "kind": "actor",
      "actor": "admin",
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
      "text": "The Product removes the comment with its reactions and hides it from the feed",
      "kind": "product",
      "actor": "admin",
      "entities": [
        {
          "entity": "comment",
          "effect": "removes"
        },
        {
          "entity": "reaction",
          "effect": "removes",
          "with": "comment"
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

# Delete a member's comment

## Trigger

A comment should not stay in the team's record.

## Outcome

The comment is gone; a standard member trying the same is refused.
