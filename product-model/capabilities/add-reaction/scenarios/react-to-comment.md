---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Standard member picks an emoji on a comment",
      "kind": "actor",
      "actor": "standard-member",
      "entities": [
        {
          "entity": "comment",
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
      "text": "The Product records the reaction once per member and emoji",
      "kind": "product",
      "actor": "standard-member",
      "entities": [
        {
          "entity": "reaction",
          "effect": "creates",
          "facts": [
            "Emoji"
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
      "text": "The Product notifies the comment's author, unless the member reacted to their own comment",
      "kind": "product",
      "actor": "standard-member",
      "entities": [
        {
          "entity": "notification",
          "effect": "creates",
          "to": "Unread",
          "facts": [
            "Kind",
            "Emoji",
            "Created at"
          ]
        },
        {
          "entity": "comment",
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

# React to a comment

## Trigger

A member agrees with or acknowledges a comment.

## Outcome

The reaction shows on the comment with who reacted, and the author's panel groups everyone who reacted into one row.

## Edge cases

- An emoji outside the offered set is refused.
- Adding back a reaction that was taken back does not notify the author again.
