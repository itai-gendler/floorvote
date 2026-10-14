---
{
  "availability": [
    {
      "place": "instance-web::workspace"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/queue/processor.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/lib/llm.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/lib/healStalledAi.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/cron/sync.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "central/src/routes/tenants.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "central/src/cron/sync.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "shared/keywords.ts"
    }
  ]
}
---

# Deliver bill updates

The instance keeps its bills current from the operator's central service, which reads every covered state's legislative data on a schedule. Every bill arrives to browse; bills matching the keywords, and bills the team tracks by hand, are also analyzed by AI with the instance's own instructions, and their changes reach the feed and the calendar.
