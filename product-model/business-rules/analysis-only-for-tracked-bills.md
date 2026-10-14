---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "deliver-bill-updates"
    },
    {
      "type": "capability",
      "id": "reanalyze-bills"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/queue/processor.ts"
    }
  ]
}
---

# AI analyzes only tracked bills that have full text

Untracked bills are never sent to the AI. A tracked bill is analyzed only once the legislature has published its text, and not again while its text is unchanged unless an admin asks for re-analysis. Prioritizing an untracked bill is how it gets analyzed without matching a keyword.
