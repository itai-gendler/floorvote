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
      "target": "api/src/lib/llm.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "shared/aiDefaults.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/pages/admin/aiConfig.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/pages/admin/TagTaxonomyTable.tsx"
    }
  ]
}
---

# Change AI instructions

An admin writes the directions the AI follows when it summarizes a bill, the question it answers to score relevance, and the tag taxonomy it tags from. Empty directions fall back to defaults that name the organization.
