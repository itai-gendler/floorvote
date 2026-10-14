---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "change-bill-priority"
    },
    {
      "type": "capability",
      "id": "change-official-position"
    },
    {
      "type": "capability",
      "id": "post-comment"
    },
    {
      "type": "capability",
      "id": "create-draft-bill"
    },
    {
      "type": "capability",
      "id": "deliver-bill-updates"
    },
    {
      "type": "entity",
      "id": "feed-activity"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/routes/billsApi/engagementRoutes.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/routes/billsApi/draftRoutes.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/routes/billsApi/bulkRoutes.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/queue/processor.ts"
    }
  ]
}
---

# The feed records activity on bills

Setting a priority or an official position, posting a comment and creating a draft are recorded with who did it. The instance records new keyword matches once, changes to analyzed tracked bills, and hearings added, changed or cancelled. A bulk edit of more than ten bills is one entry. Clearing a position on a bill hides its entries, deleting a comment hides its entry, and editing a comment updates its preview.
