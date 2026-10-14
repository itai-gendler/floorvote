---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Standard member opens the feed",
      "kind": "actor",
      "actor": "standard-member",
      "entities": [],
      "contexts": {
        "web": {
          "place": "instance-web::workspace::feed"
        }
      }
    },
    {
      "text": "The Product lists feed activity grouped by bill and day, leaving out automatic updates on bills without a priority unless a member acted on that bill the same day",
      "kind": "product",
      "actor": "standard-member",
      "entities": [
        {
          "entity": "feed-activity",
          "effect": "reads",
          "facts": [
            "Kind",
            "Actor",
            "Details",
            "Bills",
            "When"
          ]
        },
        {
          "entity": "bill",
          "effect": "reads",
          "facts": [
            "Bill number",
            "Title",
            "Priority",
            "Summary"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "instance-web::workspace::feed"
        }
      }
    },
    {
      "text": "The Product records that the member has seen the feed",
      "kind": "product",
      "actor": "standard-member",
      "entities": [
        {
          "entity": "member-account",
          "effect": "changes",
          "facts": [
            "Feed last seen"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "instance-web::workspace::feed"
        }
      }
    }
  ]
}
---

# Read the team feed

## Trigger

A member wants to catch up on what the team and the legislature did.

## Outcome

The member sees the team's recent activity, and the feed's unread dot stays off until someone else does something the feed shows.

## Edge cases

- A bulk edit of more than ten bills appears as one entry that lists its bills when expanded.
- Activity by a deactivated member is hidden.
- The member's own activity never lights the unread dot.
