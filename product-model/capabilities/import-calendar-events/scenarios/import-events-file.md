---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Admin uploads a spreadsheet or .ics file of up to 1,000 events",
      "kind": "actor",
      "actor": "admin",
      "entities": [],
      "contexts": {
        "web": {
          "place": "instance-web::workspace::calendar"
        }
      }
    },
    {
      "text": "The Product adds new events as custom events, updates the ones whose content changed and skips rows without a title or date",
      "kind": "product",
      "actor": "admin",
      "entities": [
        {
          "entity": "custom-event",
          "effect": "creates",
          "to": "Confirmed",
          "facts": [
            "Title",
            "Date",
            "Time",
            "Location",
            "Details",
            "Link"
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
      "text": "The Product reports how many were created, updated, unchanged and skipped",
      "kind": "product",
      "actor": "admin",
      "entities": [],
      "contexts": {
        "web": {
          "place": "instance-web::workspace::calendar"
        }
      }
    }
  ]
}
---

# Import a file of events

## Trigger

The team keeps its schedule in a spreadsheet or another calendar.

## Outcome

The events are on the team calendar; a file of more than 1,000 rows is refused.

## Edge cases

- An .ics event keeps its own identity across imports, so a retitled or moved event updates; a spreadsheet row is recognized by its date and title.
