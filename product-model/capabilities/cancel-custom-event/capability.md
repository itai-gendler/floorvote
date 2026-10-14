---
{
  "availability": [
    {
      "place": "instance-web::workspace"
    }
  ],
  "domain": "calendar",
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "api/src/routes/calendarApi.ts"
    }
  ]
}
---

# Cancel custom event

An admin cancels a custom event. Deleting an event on the calendar cancels it, so subscribed calendar apps see the cancellation.
