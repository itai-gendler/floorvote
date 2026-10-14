---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "member-account",
      "effect": "changes",
      "facts": [
        "Name",
        "Subtitle",
        "Digest emails",
        "Week-ahead emails",
        "Reply emails",
        "Feed last seen"
      ]
    }
  ],
  "permits": [
    {
      "related": [
        {
          "verb": "holds",
          "entity": "standard-member"
        }
      ]
    },
    {
      "related": [
        {
          "verb": "holds",
          "entity": "admin"
        }
      ]
    },
    {
      "related": [
        {
          "verb": "holds",
          "entity": "owner"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/routes/users.ts"
    }
  ]
}
---

# Members change only their own profile and email choices

A member's name, subtitle and email choices, and when they last read the feed, are theirs alone to change.
