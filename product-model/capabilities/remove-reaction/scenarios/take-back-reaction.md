---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Standard member removes their emoji from a comment",
      "kind": "actor",
      "actor": "standard-member",
      "entities": [
        {
          "entity": "reaction",
          "effect": "reads",
          "facts": [
            "Emoji"
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
    },
    {
      "text": "The Product removes the member's reaction",
      "kind": "product",
      "actor": "standard-member",
      "entities": [
        {
          "entity": "reaction",
          "effect": "removes"
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

# Take back a reaction

## Trigger

A member reacted by mistake.

## Outcome

The reaction is gone; the notification it sent the author stays.
