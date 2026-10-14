---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/lib/notifications.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/db/schema.ts"
    }
  ]
}
---

# Notification

One item in a member's notifications panel, telling them about something that happened in a bill's comments: a mention, a reply or a reaction.

## Information kept

- **Kind** — Mention, Reply or Reaction
- **Reached through** — for a mention, whether it named the member, one of their roles, or everyone
- **Emoji** — for a reaction, the emoji used
- **Created at** — when the event happened

## States

### Unread

The member has not opened the panel or the bill since it arrived.

### Read

The member opened the notifications panel or the bill.
