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
      "target": "api/src/routes/exportApi.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "shared/exportTables.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/lib/exportData.ts"
    }
  ]
}
---

# Export instance data

An admin downloads the instance's data as CSV or JSON, together with the legislature's amendments, supplements and roll calls for its tracked bills.
