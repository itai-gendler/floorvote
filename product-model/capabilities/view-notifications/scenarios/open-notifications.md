---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Standard member opens the notifications panel",
      "kind": "actor",
      "actor": "standard-member",
      "entities": [
        {
          "entity": "notification",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "web": {
          "place": "instance-web::workspace::notifications"
        }
      }
    },
    {
      "text": "The Product lists the member's mentions and replies newest first, and emoji responses to their comments grouped one row per comment",
      "kind": "product",
      "actor": "standard-member",
      "entities": [
        {
          "entity": "notification",
          "effect": "reads",
          "facts": [
            "Kind",
            "Reached through",
            "Emoji",
            "Created at"
          ]
        },
        {
          "entity": "comment",
          "effect": "reads",
          "facts": [
            "Content"
          ]
        },
        {
          "entity": "bill",
          "effect": "reads",
          "facts": [
            "Bill number",
            "Title"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "instance-web::workspace::notifications"
        }
      }
    },
    {
      "text": "The Product marks every unread notification read",
      "kind": "product",
      "actor": "standard-member",
      "entities": [
        {
          "entity": "notification",
          "effect": "changes",
          "from": "Unread",
          "to": "Read",
          "facts": []
        }
      ],
      "contexts": {
        "web": {
          "place": "instance-web::workspace::notifications"
        }
      }
    }
  ]
}
---

# Open the notifications panel

## Trigger

The unread count on the notifications bell shows something new.

## Outcome

The member sees what happened in the comments that concern them, and the unread count clears.

## Edge cases

- A notification whose comment was deleted, or whose author was deactivated, is hidden.
- Taking a reaction back leaves the notification it already sent.
