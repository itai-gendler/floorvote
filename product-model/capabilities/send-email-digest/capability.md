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
      "target": "api/src/lib/digest.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/lib/digestEmail.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/index.ts"
    }
  ]
}
---

# Send email digest

When the instance has the digest on, it emails members what changed on prioritized bills since the last digest — status changes, hearings, positions, priorities and comments — and gives admins the new keyword matches waiting for triage too.
