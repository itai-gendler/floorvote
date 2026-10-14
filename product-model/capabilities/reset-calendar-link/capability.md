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
      "target": "api/src/routes/calendarApi.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/pages/admin/Config.tsx"
    }
  ]
}
---

# Reset calendar link

An admin replaces the calendar subscription's secret link, so the old link stops working.
