---
{
  "kind": "configuration",
  "of": "capability-scenario",
  "settings": [
    {
      "entity": "instance-settings",
      "fact": "Covered states"
    }
  ],
  "takesEffect": "When an admin creates a draft. The covered states are fixed when the instance is deployed.",
  "stability": "A draft keeps the state it was created in, and an admin can move it to another state by editing it.",
  "alternatives": [
    {
      "id": "create-draft-in-its-state",
      "selectedWhen": "The instance covers a single state: the draft takes that state and the admin does not choose one."
    },
    {
      "id": "create-draft-choosing-state",
      "selectedWhen": "The instance covers several states: the admin chooses the draft's state, and a draft without one is refused."
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/routes/billsApi/draftRoutes.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/pages/admin/DraftBills.tsx"
    }
  ]
}
---

# Draft bill state

An instance deployed for one state puts every draft in that state; an instance covering several states asks which state a draft belongs to. Both kinds of deployment are supported.
