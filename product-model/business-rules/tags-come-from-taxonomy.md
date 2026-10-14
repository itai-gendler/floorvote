---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "deliver-bill-updates"
    },
    {
      "type": "capability",
      "id": "change-ai-instructions"
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
      "target": "api/src/lib/taxonomy.ts"
    }
  ]
}
---

# AI tags come only from the instance's tag taxonomy

Any tag the AI proposes that is not in the taxonomy is dropped before it is stored. Without a saved taxonomy, a default one applies. Relevance is always a score from 1 to 10.
