---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "bill",
      "effect": "changes",
      "facts": [
        "Analysis"
      ]
    }
  ],
  "permits": [
    {
      "actors": [
        "admin",
        "owner"
      ]
    },
    {
      "unattended": true
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/routes/adminApi.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/queue/processor.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/lib/healStalledAi.ts"
    }
  ]
}
---

# Only admins and owners ask for bills to be analyzed again; otherwise the instance decides

The instance analyzes tracked bills as their text arrives and retries stalled analyses hourly; re-analysis on request is for admins and owners.
