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
      "target": "api/src/lib/keywordMatchSummary.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "shared/keywords.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/pages/admin/Config.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/pages/admin/KeywordMatchSummary.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/cron/sync.ts"
    }
  ]
}
---

# Change bill keywords

An admin edits the keywords that decide which bills the instance tracks. While they type, the box shows how many of the instance's bills the list matches and how many saving would newly match or unmatch; nothing is saved and no AI runs until they save.
