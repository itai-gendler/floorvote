---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "deliver-bill-updates"
    },
    {
      "type": "capability",
      "id": "change-bill-keywords"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "shared/keywords.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/lib/keywords.ts"
    },
    {
      "kind": "doc",
      "role": "intent",
      "target": "docs/content/overview/what-can-it-do.md",
      "title": "Set keywords for the topics you care about"
    }
  ]
}
---

# A bill matches when its title, description or number matches a keyword

A keyword without wildcards matches a whole word, where letters and digits are both part of a word; `*` matches any run of characters and relaxes the word boundary on its side; `#` matches exactly one digit. A list holding only `*` matches every bill, and an empty list matches none. Matching ignores case.

## Rationale

The same matcher decides both which bills central delivers in full and which ones the instance analyzes, so the two never disagree.
