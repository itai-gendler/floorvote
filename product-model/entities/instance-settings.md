---
{
  "singleton": true,
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/routes/adminApi.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/routes/configApi.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/db/schema.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "shared/modules.ts"
    }
  ]
}
---

# Instance settings

The one set of settings an instance keeps for its organization: what it tracks, how bills are analyzed, which emails go out and how the calendar is shared. Each team's instance is its own deployment, so these settings belong to one organization only. Covered states, demo mode, sign-in verification and legal terms are set by the operator when the instance is deployed; admins change the rest in Settings.

## Information kept

- **Name** — the organization name shown in the app, its emails and the calendar subscription title
- **Organization noun** — the word the app uses for the organization: team, association, coalition or a custom word
- **Covered states** — the states, the District of Columbia or Congress whose legislation the instance follows
- **Keywords** — the keyword list that decides which bills the instance tracks, in the keyword syntax
- **AI context** — the directions the AI follows when it summarizes a bill
- **Relevance question** — the question the AI answers when it scores how relevant a bill is
- **Tag taxonomy** — the tags the AI may apply to a bill, each with a description
- **New match minimum relevance** — the relevance score a new keyword match needs to wait in New matches and the admin digest
- **Conversation emails** — whether mentions and replies are emailed as well as shown in the app
- **Email digest** — whether the digest of activity on prioritized bills is sent, daily or weekly, and on which weekday
- **Week-ahead email** — whether the weekly preview of upcoming events is sent, and on which weekday
- **Sidebar widgets** — whether the Prioritized bills and Upcoming hearings widgets show in every member's sidebar
- **Calendar event rules** — which committees, kinds of event, topics and tracked-bill agendas select the legislature events the instance shows
- **Calendar feed link** — the secret address calendar apps subscribe to
- **Account deletion** — whether accounts can be deleted permanently, or only deactivated
- **Demo mode** — whether the deployment is a public demo that visitors enter without signing in
- **Sign-in verification** — whether a request for a sign-in link must pass a human verification check
- **Legal terms** — the date of the terms members must accept, when the operator publishes terms
