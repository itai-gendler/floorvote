---
{
  "relations": [
    {
      "entity": "member-vote",
      "verb": "receives",
      "cardinality": "one-to-many"
    },
    {
      "entity": "comment",
      "verb": "has",
      "cardinality": "one-to-many"
    },
    {
      "entity": "personal-note",
      "verb": "has",
      "cardinality": "one-to-many"
    },
    {
      "entity": "calendar-entry",
      "verb": "has",
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
      "target": "api/src/queue/processor.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/routes/billsApi/detail.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "shared/statusStages.ts"
    }
  ]
}
---

# Bill

A piece of legislation the instance holds: a bill filed in one of its covered states, kept current from the legislature's data, or a draft an admin tracks before it is filed. Every bill in the covered states is available to browse; the bills the team tracks are also summarized, tagged and scored by AI.

## Information kept

- **Bill number** — the number the legislature gave the bill, or a draft number such as DRAFT-1
- **Title** — the bill's title; a draft may be untitled
- **State** — the state, the District of Columbia or Congress the bill belongs to
- **Session** — the legislative session and its years
- **Status** — the legislature's own name for where the bill stands
- **Stage** — the common step the status belongs to: Introduced, In committee, Passed one chamber, Passed legislature, Failed, Vetoed or Enacted
- **Abstract** — the legislature's description of the bill
- **Sponsors** — the primary sponsor and co-sponsors, with party
- **Last action** — the latest action and its date
- **History** — every recorded action, with date and chamber
- **Committee** — the committee the bill is pending in, and its referrals
- **Texts** — each published version of the bill's text, with fiscal notes, amendments and other documents
- **Roll-call votes** — the legislature's recorded votes on the bill
- **Subjects** — the subjects the legislature filed the bill under
- **Provider details** — fields only the bill's data provider publishes, shown in their own panel
- **Summary** — the AI's plain-language summary, or a draft's summary written by an admin
- **Tags** — the tags the AI applied from the instance's tag taxonomy
- **Relevance score** — the AI's relevance score, from 1 to 10
- **Analysis** — whether AI analysis is done, pending, or not possible for the bill's text
- **Priority** — High, Medium or Low, set by an admin, or none
- **Official position** — the team's position: Support, Oppose, Amend, Monitor or No Position, with who set it
- **Custom field values** — the value of each custom field, with who set it
- **New match** — when the bill first became an analyzed keyword match
- **Triaged** — when and by whom the new match was triaged, by a priority or a dismissal
- **Vote tally** — how many members voted support, oppose and neutral
- **Draft text** — the text an admin keeps for a draft

## States

### Untracked

The bill is in a covered state and available to browse, without AI analysis.

### Matched

The bill matches the instance's keywords and is tracked and analyzed.

### Added

The team tracks the bill by hand: an admin prioritized it, or it stopped matching the keywords after the team engaged with it.

### Draft

An admin tracks the bill before it is filed; it has no legislative data until it is linked to its filed bill.
