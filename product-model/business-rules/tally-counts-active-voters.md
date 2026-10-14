---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "view-bill"
    },
    {
      "type": "capability",
      "id": "browse-bills"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/routes/billsApi/detail.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/routes/billsApi/listRoutes.ts"
    }
  ]
}
---

# Vote tallies count only active members whose voting is allowed

Votes cast by members who are later restricted from voting, or deactivated, stay recorded but drop out of the tally until the member can vote again or is reactivated.
