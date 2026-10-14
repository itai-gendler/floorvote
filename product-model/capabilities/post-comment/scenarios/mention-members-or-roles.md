---
{
  "kind": "alternative",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Standard member @-mentions members or a role in a message on a bill and posts it",
      "kind": "actor",
      "actor": "standard-member",
      "entities": [
        {
          "entity": "bill",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "role",
          "effect": "reads",
          "facts": [
            "Name"
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
      "text": "The Product saves the comment with its mentions",
      "kind": "product",
      "actor": "standard-member",
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
      "text": "The Product gives each mentioned member, and each member of a mentioned role who has signed in, one mention, attributed to a direct mention first and the role second",
      "kind": "product",
      "actor": "standard-member",
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
        },
        {
          "entity": "role",
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
      "text": "The Product emails each person reached, unless conversation emails are off",
      "kind": "product",
      "actor": "standard-member",
      "entities": [
        {
          "entity": "member-account",
          "effect": "reads",
          "facts": [
            "Email"
          ]
        },
        {
          "entity": "instance-settings",
          "effect": "reads",
          "facts": [
            "Conversation emails"
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

# Mention members or a role

## Trigger

A member wants a colleague or a committee to look at a bill.

## Outcome

Everyone the comment reaches has a mention in their panel and, unless conversation emails are off, an email that says why they received it.

## Edge cases

- The author is never notified of their own mention.
- A person reached both directly and through a role gets one mention.
