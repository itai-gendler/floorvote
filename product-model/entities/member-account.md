---
{
  "relations": [
    {
      "entity": "member-vote",
      "verb": "casts",
      "cardinality": "one-to-many"
    },
    {
      "entity": "comment",
      "verb": "writes",
      "cardinality": "one-to-many"
    },
    {
      "entity": "personal-note",
      "verb": "keeps",
      "cardinality": "one-to-many"
    },
    {
      "entity": "reaction",
      "verb": "places",
      "cardinality": "one-to-many"
    },
    {
      "entity": "notification",
      "verb": "receives",
      "cardinality": "one-to-many"
    },
    {
      "entity": "login-activity",
      "verb": "has",
      "cardinality": "one-to-many"
    },
    {
      "entity": "sign-in-link",
      "verb": "requests",
      "cardinality": "one-to-many"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/db/schema.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/lib/pendingInvite.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/lib/loginHistory.ts"
    }
  ]
}
---

# Member account

A person's login in one instance, whatever their permission level: the address they sign in with, how they appear to the team and which emails they want. Each Standard member, Admin and Owner holds exactly one.

## Information kept

- **Email** — the address the member signs in with and receives email at
- **Name** — the name shown to the team; an account without one shows its email
- **Subtitle** — a short line shown under the name, such as a title or organization
- **Permission level** — Owner, Admin or Standard member
- **Voting** — Allowed, or Restricted when an admin keeps the member from voting
- **Roles** — the roles the member belongs to
- **Invited by** — the member who invited them
- **Digest emails** — whether the member receives the email digest
- **Week-ahead emails** — whether the member receives the week-ahead email
- **Reply emails** — whether the member is emailed when someone comments on a bill they commented on
- **Accepted terms** — the date of the newest legal terms the member accepted
- **Last active** — when the member last used the instance
- **Feed last seen** — when the member last read the feed
- **Email bounced** — whether the latest invite or sign-in email to a pending invite bounced, with the receiving server's reason

## States

### Pending invite

An admin invited the person and they have not signed in yet.

### Active

The member has signed in at least once and can use the instance.

### Deactivated

The member cannot sign in, and their votes, comments and activity are hidden, until an admin reactivates them.
