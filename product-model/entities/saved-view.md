---
{
  "domain": "bills",
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/routes/savedViewsApi.ts"
    }
  ]
}
---

# Saved view

A named set of bill filters an admin saves for the whole team, which every member can switch to on the Bills page.

## Information kept

- **Name** — the view's name
- **Filters** — the filters, search and sort the view applies
- **Link name** — the name its bookmarkable link uses; a renamed view keeps answering to its previous link name
- **Order** — where the view appears in the switcher
