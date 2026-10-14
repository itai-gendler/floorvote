---
{
  "kind": "alternative",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Standard member switches the feed to all fully analyzed bills",
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
          "place": "instance-web::workspace::feed"
        }
      }
    },
    {
      "text": "The Product lists every feed activity on tracked bills, including new keyword matches and status changes on bills without a priority",
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
    }
  ]
}
---

# Read all activity on analyzed bills

## Trigger

A member wants the complete record of what changed on tracked bills.

## Outcome

The member sees every activity on tracked bills, not only prioritized ones.
