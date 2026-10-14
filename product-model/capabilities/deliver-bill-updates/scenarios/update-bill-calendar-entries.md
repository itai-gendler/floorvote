---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The central service delivers the calendar of a bill the instance tracks or has prioritized",
      "kind": "condition",
      "unattended": true,
      "entities": [
        {
          "entity": "bill",
          "effect": "reads",
          "facts": [
            "Priority"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "instance-web::workspace::calendar"
        }
      }
    },
    {
      "text": "The Product adds new hearings, markups, meetings and deadlines, and updates changed ones, raising their sequence",
      "kind": "product",
      "entities": [
        {
          "entity": "calendar-entry",
          "effect": "creates",
          "as": "scheduled",
          "to": "Confirmed",
          "facts": [
            "Kind",
            "Date",
            "Time",
            "Location",
            "Description",
            "Covered by"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "instance-web::workspace::calendar"
        }
      }
    },
    {
      "text": "The Product marks entries the legislature no longer lists cancelled",
      "kind": "product",
      "entities": [
        {
          "entity": "calendar-entry",
          "effect": "changes",
          "as": "dropped",
          "from": "Confirmed",
          "to": "Cancelled",
          "facts": []
        }
      ],
      "contexts": {
        "web": {
          "place": "instance-web::workspace::calendar"
        }
      }
    }
  ]
}
---

# Update a bill's calendar entries

## Trigger

The legislature schedules, moves or drops a hearing on a tracked bill.

## Outcome

The calendar and its subscribers show the change for prioritized bills, and the feed records hearings added, changed or cancelled; deadlines are not announced in the feed.

## Edge cases

- An entry that comes back after being cancelled is confirmed again under the same identity.
