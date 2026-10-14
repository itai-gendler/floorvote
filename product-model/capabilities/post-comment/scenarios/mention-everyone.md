---
{
  "kind": "alternative",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Admin @-mentions everyone in a message on a bill and posts it",
      "kind": "actor",
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
          "place": "instance-web::workspace::bill"
        }
      }
    },
    {
      "text": "The Product saves the comment with its mentions",
      "kind": "product",
      "actor": "admin",
      "entities": [
        {
          "entity": "comment",
          "effect": "creates",
          "facts": [
            "Content",
            "Mentions",
            "Posted at"
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
      "text": "The Product gives every member who has signed in a mention reached through everyone",
      "kind": "product",
      "actor": "admin",
      "entities": [
        {
          "entity": "notification",
          "effect": "creates",
          "to": "Unread",
          "facts": [
            "Kind",
            "Reached through",
            "Created at"
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

# Notify everyone

## Trigger

An admin needs the whole team to see a bill.

## Outcome

Every active member has a mention saying an admin notified everyone; a standard member's @everyone reaches nobody.
