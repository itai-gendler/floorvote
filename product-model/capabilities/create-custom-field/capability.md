---
{
  "availability": [
    {
      "place": "instance-web::settings"
    }
  ],
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
      "target": "web/src/pages/admin/Config.tsx"
    }
  ]
}
---

# Create custom field

An admin defines a custom field for bills: a checkbox, a dropdown of one or several values, a text field or a date.
