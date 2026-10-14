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
      "target": "web/src/components/dragReorder.tsx"
    }
  ]
}
---

# Reorder custom fields

An admin drags custom fields into the order bills show them in.
