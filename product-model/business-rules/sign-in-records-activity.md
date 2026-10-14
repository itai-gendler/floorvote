---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "member-account",
      "effect": "changes",
      "facts": [
        "Last active"
      ]
    }
  ],
  "permits": [
    {
      "actors": [
        "visitor"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/routes/auth.ts"
    }
  ]
}
---

# Signing in records when the member was last active

A member's last active time is set by their own sign-in and use of the instance, never by someone else.
