---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Owner chooses to clear all interactions and confirms",
      "kind": "actor",
      "actor": "owner",
      "entities": [],
      "contexts": {
        "web": {
          "place": "instance-web::settings::config"
        }
      }
    },
    {
      "text": "The Product removes every vote, comment, reaction and personal note, and every bill's priority and official position",
      "kind": "product",
      "actor": "owner",
      "entities": [
        {
          "entity": "member-vote",
          "effect": "removes"
        },
        {
          "entity": "comment",
          "effect": "removes"
        },
        {
          "entity": "reaction",
          "effect": "removes",
          "with": "comment"
        },
        {
          "entity": "personal-note",
          "effect": "removes"
        },
        {
          "entity": "bill",
          "effect": "changes",
          "facts": [
            "Priority",
            "Official position"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "instance-web::settings::config"
        }
      }
    }
  ]
}
---

# Clear the team's activity

## Trigger

An instance used for a trial or a past session starts fresh.

## Outcome

The team starts over with its members, bills and summaries intact; this cannot be undone.
