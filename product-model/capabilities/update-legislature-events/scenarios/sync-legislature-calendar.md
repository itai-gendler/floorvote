---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The hourly run finds a covered state whose data includes the legislature's calendar",
      "kind": "condition",
      "unattended": true,
      "entities": [
        {
          "entity": "instance-settings",
          "effect": "reads",
          "facts": [
            "Covered states"
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
      "text": "The Product adds and updates the legislature events, linking the bills on each agenda",
      "kind": "product",
      "entities": [
        {
          "entity": "legislature-event",
          "effect": "creates",
          "to": "Confirmed",
          "facts": [
            "Title",
            "Date",
            "Time",
            "Location",
            "Committee",
            "Kind",
            "Agenda"
          ]
        },
        {
          "entity": "bill",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "web": {
          "place": "instance-web::workspace::calendar"
        }
      }
    },
    {
      "text": "The Product applies the calendar event rules, always showing an event with a prioritized bill on its agenda",
      "kind": "product",
      "entities": [
        {
          "entity": "instance-settings",
          "effect": "reads",
          "facts": [
            "Calendar event rules"
          ]
        },
        {
          "entity": "legislature-event",
          "effect": "changes",
          "facts": [
            "Shown"
          ]
        },
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
      "text": "The Product marks the bill calendar entries each shown legislature event covers, so a hearing appears once",
      "kind": "product",
      "entities": [
        {
          "entity": "calendar-entry",
          "effect": "changes",
          "facts": [
            "Covered by"
          ]
        },
        {
          "entity": "legislature-event",
          "effect": "reads",
          "facts": [
            "Shown"
          ]
        },
        {
          "entity": "bill",
          "effect": "reads",
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

# Bring in the legislature's calendar

## Trigger

The legislature publishes or changes its calendar.

## Outcome

The calendar shows the selected legislature events, with or without bills on their agendas.

## Edge cases

- An event the legislature cancels shows as cancelled; one it drops is removed.
- A central outage changes nothing, and the next hour tries again.
