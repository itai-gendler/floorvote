---
{
  "domain": "config",
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/routes/customFieldsApi.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "shared/customFieldValues.ts"
    }
  ]
}
---

# Custom field

A field the team defines for its bills, such as a "Testimony submitted" checkbox or a "Lead person" dropdown, filled in per bill.

## Information kept

- **Name** — the field's name
- **Type** — Checkbox, Dropdown, Text or Date
- **Options** — the choices of a dropdown
- **Multiple** — whether a dropdown takes several values
- **Pinned** — whether a text field's value shows above the bill's summary
- **Order** — where the field appears among the others
