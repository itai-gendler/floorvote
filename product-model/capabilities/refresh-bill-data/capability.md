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
      "target": "api/src/routes/adminApi.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/lib/refreshMetadata.ts"
    }
  ]
}
---

# Refresh bill data

An admin refreshes every bill's legislative data — sponsors, history, status — from the central service, leaving AI summaries untouched.
