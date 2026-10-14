---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/lib/authEvents.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/routes/users.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/routes/adminApi.ts"
    }
  ]
}
---

# Login activity

One entry in a member's login history: a sign-in link or invite requested or emailed, a sign-in, a failed sign-in, a sign-out, or an address change.

## Information kept

- **Event** — what happened
- **Link kind** — whether a link was a sign-in link or an invite
- **Changed by** — the member who caused it, when it was not the member themselves
- **Country** — the country the request came from
- **Device** — the browser that made the request
- **When** — when it happened
