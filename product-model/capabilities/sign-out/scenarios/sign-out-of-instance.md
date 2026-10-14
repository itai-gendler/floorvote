---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Standard member chooses to sign out",
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
      "text": "The Product ends this session and returns the member to the login page",
      "kind": "product",
      "actor": "standard-member",
      "entities": [
        {
          "entity": "member-account",
          "effect": "reads",
          "facts": []
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

# Sign out

## Trigger

A member is done using the instance on this device.

## Outcome

This device is signed out; sessions on other devices continue.
