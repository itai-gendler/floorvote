---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The daily morning run finds the digest on and due",
      "kind": "condition",
      "unattended": true,
      "entities": [
        {
          "entity": "instance-settings",
          "effect": "reads",
          "facts": [
            "Email digest"
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
      "text": "The Product gathers the feed activity on prioritized bills since the last digest, and the untriaged new matches above the threshold",
      "kind": "product",
      "entities": [
        {
          "entity": "feed-activity",
          "effect": "reads",
          "facts": [
            "Kind",
            "Actor",
            "Details",
            "When"
          ]
        },
        {
          "entity": "bill",
          "effect": "reads",
          "facts": [
            "Bill number",
            "Title",
            "Summary",
            "Priority",
            "Relevance score",
            "New match"
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
      "text": "The Product emails the digest to every active member who keeps digest emails on, adding the new matches for admins and owners",
      "kind": "product",
      "entities": [
        {
          "entity": "member-account",
          "effect": "reads",
          "facts": [
            "Email",
            "Digest emails",
            "Permission level"
          ]
        },
        {
          "entity": "admin",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "owner",
          "effect": "reads",
          "facts": []
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

# Send the digest

## Trigger

It is the digest's time: every morning (UTC) for a daily digest, or the chosen weekday for a weekly one.

## Outcome

Members catch up on prioritized bills from their inbox; a weekly digest covers the whole week.

## Edge cases

- With nothing on prioritized bills, standard members get no digest and admins get one only for new matches.
- Activity by deactivated members is left out.
- A demo instance never sends it.
