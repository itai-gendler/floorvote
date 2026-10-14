---
{
  "entities": [
    {
      "entity": "bill",
      "shows": [
        "Bill number",
        "Title",
        "State",
        "Sponsors",
        "Summary"
      ],
      "collects": [
        "Bill number",
        "Title",
        "State",
        "Summary",
        "Draft text",
        "Custom field values"
      ]
    },
    {
      "entity": "instance-settings",
      "shows": [
        "Covered states"
      ]
    },
    {
      "entity": "custom-field",
      "shows": [
        "Name",
        "Type",
        "Options"
      ]
    }
  ],
  "entryPoints": [
    {
      "instance-web": "/admin/drafts"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/pages/admin/DraftBills.tsx"
    }
  ]
}
---

# Draft bills

The instance's draft bills, and the form that creates one.
