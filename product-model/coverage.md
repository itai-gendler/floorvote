---
{
  "scope": "The team instance's API, web app and shared code, and the central service's routes and jobs that register instances and deliver bills, calendars and legislature events to them.",
  "method": "Static reading of source, schema, migrations, documentation and tests at the pinned commit; nothing was run.",
  "covered": [
    {
      "description": "Instance API: routes, middleware, queue consumers and scheduled jobs.",
      "paths": [
        "api/src/"
      ]
    },
    {
      "description": "Instance database migrations.",
      "paths": [
        "api/migrations/"
      ]
    },
    {
      "description": "Instance web app pages and components.",
      "paths": [
        "web/src/"
      ]
    },
    {
      "description": "Definitions shared by the instance API and web app.",
      "paths": [
        "shared/"
      ]
    },
    {
      "description": "Central routes and jobs that register instances and deliver bills, calendars and legislature events.",
      "paths": [
        "central/src/routes/tenants.ts",
        "central/src/cron/sync.ts",
        "central/src/cron/body-events.ts"
      ]
    }
  ],
  "exclusions": [
    {
      "description": "Automated tests and fixtures.",
      "paths": [
        "api/test/",
        "central/test/",
        "root/test/"
      ]
    },
    {
      "description": "Documentation site, internal and agent documentation, and legal templates.",
      "paths": [
        "docs/"
      ]
    },
    {
      "description": "Build, seed, deployment and maintenance scripts.",
      "paths": [
        "scripts/",
        "central/scripts/",
        "api/deploy.sh"
      ]
    },
    {
      "description": "Generated code-graph output.",
      "paths": [
        "graphify-out/"
      ]
    },
    {
      "description": "Repository tooling: CI workflows, git hooks and agent settings.",
      "paths": [
        ".github/",
        ".githooks/",
        ".claude/"
      ]
    }
  ],
  "unmapped": [
    {
      "description": "Central operator dashboard and operator admin API (state ownership, cutovers, budgets, adoption, health, dead letters): left out as optional operator tooling the docs call not needed to run, outside a team's use.",
      "paths": [
        "central/web/",
        "central/src/routes/dash.ts",
        "central/src/routes/dash-auth.ts",
        "central/src/routes/dash-engagement.ts",
        "central/src/routes/dash-unknown-logins.ts",
        "central/src/routes/admin.ts",
        "central/src/routes/health.ts",
        "central/src/queue/"
      ]
    },
    {
      "description": "Legislative data provider adapters and vocabularies: left out as integrations owned by LegiScan and the legislatures; what they deliver is modelled as a bill's legislative data.",
      "paths": [
        "central/src/providers/"
      ]
    },
    {
      "description": "Central bill reads, change detection, snapshots, vote datasets and engagement pulls: left out as internal plumbing behind bill delivery.",
      "paths": [
        "central/src/routes/bills.ts",
        "central/src/lib/",
        "central/src/cron/sync-snapshots.ts",
        "central/src/cron/vote-datasets.ts",
        "central/src/cron/engagement-pull.ts",
        "central/src/index-legiscan.ts",
        "central/migrations-legiscan/"
      ]
    },
    {
      "description": "Apex address that points visitors to their instances: left out as a hosting convenience outside any instance.",
      "paths": [
        "root/src/"
      ]
    },
    {
      "description": "Operator access across instances, demo seeding and resets, email provider health alerts and the stats entrypoint for other workers: left out as operator plumbing and demo data.",
      "paths": [
        "api/src/lib/superadmin.ts",
        "api/src/lib/superadminCentral.ts",
        "api/src/lib/superadminRequest.ts",
        "api/src/lib/demoSeeds/",
        "api/src/lib/demoReset.ts",
        "api/src/lib/demoResetAndSeed.ts",
        "api/src/lib/emailHealthJob.ts",
        "api/src/centralApi.ts"
      ]
    }
  ],
  "limitations": [
    {
      "description": "Invite sign-in followed by the required terms acceptance is not written as a Journey, because the person changes Actor when they sign in, which pdd-kit 0.37.0 cannot express.",
      "paths": [
        "web/src/components/RequireAuth.tsx",
        "web/src/components/AcceptTerms.tsx"
      ]
    }
  ]
}
---

# Coverage
