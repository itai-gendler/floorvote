---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "change-bill-keywords",
      "contexts": [
        {
          "place": "instance-web::settings"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/routes/adminApi.ts"
    }
  ]
}
---

# Bills the team engaged with stay tracked when the keywords stop matching them

When saved keywords no longer match a keyword-matched bill, the bill stops being tracked unless it has a priority, an official position, a vote, a live comment or a non-empty personal note; such a bill is kept as added by hand instead. Bills added by hand are never downgraded by a keyword change.
