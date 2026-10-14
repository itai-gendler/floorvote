---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The morning run on the chosen weekday finds the week-ahead email on",
      "kind": "condition",
      "unattended": true,
      "entities": [
        {
          "entity": "instance-settings",
          "effect": "reads",
          "facts": [
            "Week-ahead email"
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
      "text": "The Product gathers the coming week's confirmed events that concern prioritized bills, the custom events and the selected legislature events",
      "kind": "product",
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
          "entity": "custom-event",
          "effect": "reads",
          "facts": [
            "Title",
            "Date",
            "Time",
            "Location",
            "Details",
            "Link"
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
            "Agenda"
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
    },
    {
      "text": "The Product emails the preview to every active member who keeps week-ahead emails on",
      "kind": "product",
      "entities": [
        {
          "entity": "member-account",
          "effect": "reads",
          "facts": [
            "Email",
            "Week-ahead emails"
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

# Send the week-ahead email

## Trigger

The week starts on the instance's chosen weekday.

## Outcome

Members know what is coming up this week for the team's bills.

## Edge cases

- A week with nothing on it sends no email.
- With no calendar event rules saved, only legislature events with a prioritized bill on the agenda reach the email.
