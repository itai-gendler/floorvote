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
      "target": "web/src/components/ReprocessScopeModal.tsx"
    }
  ]
}
---

# Re-analyze bills

An admin has the AI analyze tracked bills again, all of them or only prioritized ones, usually after changing the AI instructions.
