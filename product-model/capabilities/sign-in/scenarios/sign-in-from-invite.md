---
{
  "kind": "alternative",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Visitor follows the invite they were emailed and continues",
      "kind": "actor",
      "actor": "visitor",
      "entities": [
        {
          "entity": "sign-in-link",
          "effect": "reads",
          "facts": [
            "Kind"
          ]
        },
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
          "place": "instance-web::sign-in::sign-in-link"
        }
      }
    },
    {
      "text": "The Product marks the invite used, signs the person in, and their account stops being a pending invite",
      "kind": "product",
      "actor": "visitor",
      "entities": [
        {
          "entity": "sign-in-link",
          "effect": "changes",
          "from": "Active",
          "to": "Used",
          "facts": []
        },
        {
          "entity": "member-account",
          "effect": "changes",
          "from": "Pending invite",
          "to": "Active",
          "facts": [
            "Last active"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "instance-web::sign-in::sign-in-link"
        }
      }
    }
  ]
}
---

# Sign in from an invite

## Trigger

An invited person opens the invite an admin sent them.

## Outcome

The person is signed in as a member, and the Members page no longer lists them as a pending invite.

## Edge cases

- An invite stays valid for seven days from when it was sent; resending sends another link and earlier ones keep working until they expire.
