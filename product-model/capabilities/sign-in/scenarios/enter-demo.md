---
{
  "kind": "alternative",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Visitor opens the demo instance",
      "kind": "actor",
      "actor": "visitor",
      "entities": [],
      "contexts": {
        "web": {
          "place": "instance-web::sign-in::login"
        }
      }
    },
    {
      "text": "The Product signs the Visitor in to the shared demo account without a link",
      "kind": "product",
      "actor": "visitor",
      "entities": [
        {
          "entity": "member-account",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "web": {
          "place": "instance-web::sign-in::login"
        }
      }
    }
  ]
}
---

# Enter a demo instance

## Trigger

A visitor opens a demo instance to try FloorVote.

## Outcome

The visitor is signed in to the shared demo account, which every demo visitor uses.

## Edge cases

- Opening the login page itself still shows the sign-in form, so a real member can sign in to the demo.
- In a demo, votes, comments, reactions, notes, priorities, positions, custom field values, single triage and turning sidebar widgets on and off work; every other change is refused as locked in the demo.
- A demo never runs AI analysis and never sends email, and its data is reset on a schedule.
