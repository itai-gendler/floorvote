---
{
  "type": "web",
  "actors": [
    "visitor",
    "standard-member",
    "admin",
    "owner"
  ],
  "entryPoints": [
    {
      "web": "/"
    },
    {
      "web": "/login"
    },
    {
      "web": "/bills"
    },
    {
      "web": "/calendar"
    }
  ],
  "languages": [
    "en"
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/App.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/index.ts"
    }
  ]
}
---

# Instance web app

The web app of one team's instance, where people sign in, members follow and discuss bills, and admins run the instance. Each instance serves its own app on its own address.
