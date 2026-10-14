---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Standard member opens the calendar",
      "kind": "actor",
      "actor": "standard-member",
      "entities": [],
      "contexts": {
        "web": {
          "place": "instance-web::workspace::calendar"
        }
      }
    },
    {
      "text": "The Product shows the dated entries of prioritized bills, the legislature events the rules select, and custom events, merging bill calendar entries that describe the same meeting into one with all their bills",
      "kind": "product",
      "actor": "standard-member",
      "entities": [
        {
          "entity": "calendar-entry",
          "effect": "reads",
          "facts": [
            "Kind",
            "Date",
            "Time",
            "Location",
            "Description"
          ]
        },
        {
          "entity": "legislature-event",
          "effect": "reads",
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
          "entity": "custom-event",
          "effect": "reads",
          "facts": [
            "Title",
            "Date",
            "Time",
            "Location",
            "Details",
            "Link",
            "Bills"
          ]
        },
        {
          "entity": "bill",
          "effect": "reads",
          "facts": [
            "Bill number",
            "Title",
            "Priority"
          ]
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

# View the team calendar

## Trigger

A member wants to know what is coming up for the team's bills.

## Outcome

The member sees the team's calendar from 90 days back to a year ahead; cancelled entries stay visible, marked cancelled, for two days.

## Edge cases

- A bill calendar entry covered by a legislature event the instance shows appears once, as that event.
- A deadline is never merged with a meeting.
- A bill without a priority contributes nothing to the calendar.
