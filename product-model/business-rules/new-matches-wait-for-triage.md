---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "browse-bills"
    },
    {
      "type": "capability",
      "id": "dismiss-new-match"
    },
    {
      "type": "capability",
      "id": "send-email-digest"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/routes/billsApi/query.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/lib/newMatch.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/queue/processor.ts"
    }
  ]
}
---

# A new keyword match waits for triage until an admin prioritizes or dismisses it

A bill joins New matches the first time it becomes an analyzed keyword match, and shows there while its relevance reaches the threshold. The first priority or dismissal triages it for good: clearing the priority later does not bring it back, and later updates never make it new again. Bills added by hand never appear there.
