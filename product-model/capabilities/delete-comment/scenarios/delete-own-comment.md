---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Standard member deletes one of their comments",
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
      "text": "The Product removes the comment with its reactions and hides it from the feed",
      "kind": "product",
      "actor": "standard-member",
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

# Delete your comment

## Trigger

A member regrets a comment.

## Outcome

The comment, its reactions and the notifications about it no longer show on the bill, in the feed or in notifications panels.
