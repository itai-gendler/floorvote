---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Admin picks committees, kinds, topics or agendas with tracked legislation and previews the next 120 days of legislature events against them",
      "kind": "actor",
      "actor": "admin",
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
          "effect": "reads",
          "facts": [
            "Title",
            "Date",
            "Committee",
            "Kind",
            "Agenda",
            "Shown"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "instance-web::settings::calendar-event-rules"
        }
      }
    },
    {
      "text": "The Admin saves the rules",
      "kind": "actor",
      "actor": "admin",
      "entities": [],
      "contexts": {
        "web": {
          "place": "instance-web::settings::calendar-event-rules"
        }
      }
    },
    {
      "text": "The Product saves the rules and applies them to every legislature event the instance holds at once",
      "kind": "product",
      "actor": "admin",
      "entities": [
        {
          "entity": "instance-settings",
          "effect": "changes",
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
        }
      ],
      "contexts": {
        "web": {
          "place": "instance-web::settings::calendar-event-rules"
        }
      }
    }
  ]
}
---

# Save calendar event rules

## Trigger

A state's whole legislative calendar is more than the team needs.

## Outcome

The calendar and its subscription show only the selected legislature events, plus any with a prioritized bill on the agenda.

## Edge cases

- Clearing the rules shows every legislature event again.
- When the central service cannot list committees and kinds, the page says the lists may be incomplete and still offers the ones the instance knows.
