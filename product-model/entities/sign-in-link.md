---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/routes/auth.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/queue/inviteEmails.ts"
    }
  ]
}
---

# Sign-in link

A single-use link emailed to a member that signs them in: a sign-in link valid for 60 minutes, or an invite valid for seven days.

## Information kept

- **Kind** — Sign-in or Invite
- **Expires** — when the link stops working

## States

### Active

The link has not been used.

### Used

The link signed someone in and cannot be used again.
