---
{
  "availability": [
    {
      "place": "calendar-feed"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/routes/calendarApi.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/lib/ical.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/lib/calendarIcsBody.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/lib/hearingUid.ts"
    }
  ]
}
---

# Read calendar feed

A calendar app fetches the instance's calendar at its secret link. Every event keeps one identity and a rising sequence, so changes and cancellations update in place.
