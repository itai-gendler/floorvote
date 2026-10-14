---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "change-calendar-event-rules"
    },
    {
      "type": "capability",
      "id": "update-legislature-events"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "shared/eventRules.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/lib/eventRules.ts"
    }
  ]
}
---

# Calendar event rules never hide a legislature event with a prioritized bill on its agenda

An instance with no rules shows every legislature event of its covered states. Once rules are saved, an event shows when any rule selects it — a committee (optionally narrowed to a kind), a kind or event type, a topic whose keywords match its title or agenda, or a tracked bill on its agenda — and always when a prioritized bill is on its agenda, since that is the bill's hearing.
