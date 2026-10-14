---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "sign-in",
      "contexts": [
        {
          "place": "instance-web::sign-in"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/routes/auth.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/middleware/auth.ts"
    }
  ]
}
---

# Only people an instance knows can sign in

Asking for a link with an unknown address creates no account and sends nothing, and the answer is the same as for a member, so the page never reveals who is a member. Deactivated members cannot sign in.
