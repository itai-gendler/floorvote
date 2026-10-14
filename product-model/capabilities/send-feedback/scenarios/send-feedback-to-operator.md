---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Standard member writes a message of at most 20 KB and sends it",
      "kind": "actor",
      "actor": "standard-member",
      "entities": [],
      "contexts": {
        "web": {
          "place": "instance-web::workspace"
        }
      }
    },
    {
      "text": "The Product emails the message, the member's address and the page to the operator",
      "kind": "product",
      "actor": "standard-member",
      "entities": [
        {
          "entity": "member-account",
          "effect": "reads",
          "facts": [
            "Email"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "instance-web::workspace"
        }
      }
    }
  ]
}
---

# Send feedback

## Trigger

A member has a question, problem or idea about the app.

## Outcome

The operator receives the feedback by email; a failed send tells the member it could not be sent.
