---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Standard member writes a message on a bill and posts it",
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
      "text": "The Product saves the comment, keeping only the formatting the app allows",
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
      "text": "The Product gives every other member with a live comment on the bill a reply notification",
      "kind": "product",
      "actor": "standard-member",
      "entities": [
        {
          "entity": "notification",
          "effect": "creates",
          "to": "Unread",
          "facts": [
            "Kind",
            "Created at"
          ]
        },
        {
          "entity": "comment",
          "effect": "reads",
          "facts": []
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
    },
    {
      "text": "The Product emails the participants who keep reply emails on, threaded so a bill's replies group into one conversation",
      "kind": "product",
      "actor": "standard-member",
      "entities": [
        {
          "entity": "member-account",
          "effect": "reads",
          "facts": [
            "Email",
            "Reply emails"
          ]
        },
        {
          "entity": "instance-settings",
          "effect": "reads",
          "facts": [
            "Conversation emails"
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

# Comment on a bill

## Trigger

A member has something to say about a bill.

## Outcome

The comment appears on the bill and in the feed, and the bill's earlier commenters hear about it.

## Edge cases

- An empty comment, or one over 10 KB, is refused.
- Voting, writing a note or being mentioned does not make a member a participant; only commenting does.
- Pending invites and deactivated members are not notified.

## Decision points

### Conversation emails

Are conversation emails on for the instance?

- On → participants who keep reply emails on are emailed as well as notified in the app
- Off → participants are notified in the app only
