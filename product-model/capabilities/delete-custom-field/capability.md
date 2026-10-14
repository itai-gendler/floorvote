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
    }
  ]
}
---

# Delete custom field

An admin deletes a custom field along with every bill's value for it.
