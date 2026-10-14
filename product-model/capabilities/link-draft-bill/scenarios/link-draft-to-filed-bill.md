---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Admin picks the filed bill on the draft's page and links them",
      "kind": "actor",
      "actor": "admin",
      "entities": [
        {
          "entity": "bill",
          "effect": "reads",
          "as": "draft",
          "facts": [
            "Bill number",
            "Title"
          ]
        },
        {
          "entity": "bill",
          "effect": "reads",
          "as": "filed",
          "facts": [
            "Bill number",
            "Title"
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
      "text": "The Product moves the draft's engagement, position, custom field values and calendar links to the filed bill, keeping the filed bill's where both have one",
      "kind": "product",
      "actor": "admin",
      "entities": [
        {
          "entity": "bill",
          "effect": "changes",
          "as": "filed",
          "facts": [
            "Official position",
            "Custom field values"
          ]
        },
        {
          "entity": "custom-field",
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
      "text": "The Product deletes the draft and opens the filed bill",
      "kind": "product",
      "actor": "admin",
      "entities": [
        {
          "entity": "bill",
          "effect": "removes",
          "as": "draft",
          "from": "Draft"
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

# Link a draft to its filed bill

## Trigger

The bill the team prepared for is introduced.

## Outcome

The filed bill carries the team's earlier engagement, and the draft is gone.

## Edge cases

- Linking to another draft, to itself, or to a bill that does not exist is refused.
