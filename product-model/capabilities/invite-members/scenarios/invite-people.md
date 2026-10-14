---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Admin enters names and email addresses and chooses the permission level they join at",
      "kind": "actor",
      "actor": "admin",
      "entities": [],
      "contexts": {
        "web": {
          "place": "instance-web::settings::members"
        }
      }
    },
    {
      "text": "The Product creates a pending invite for each new, valid address and emails each an invite, paced a few seconds apart",
      "kind": "product",
      "actor": "admin",
      "entities": [
        {
          "entity": "member-account",
          "effect": "creates",
          "to": "Pending invite",
          "facts": [
            "Email",
            "Name",
            "Permission level",
            "Invited by"
          ]
        },
        {
          "entity": "sign-in-link",
          "effect": "creates",
          "to": "Active",
          "facts": [
            "Kind",
            "Expires"
          ],
          "with": "member-account"
        }
      ],
      "contexts": {
        "web": {
          "place": "instance-web::settings::members"
        }
      }
    },
    {
      "text": "The Product reports which addresses were invited, already belong to a member, were repeated, invalid, or previously bounced",
      "kind": "product",
      "actor": "admin",
      "entities": [],
      "contexts": {
        "web": {
          "place": "instance-web::settings::members"
        }
      }
    }
  ]
}
---

# Invite people

## Trigger

A team is onboarding its members.

## Outcome

Each invited person has a pending invite on the Members page and an invite in their inbox.

## Edge cases

- An address that bounced before from this instance, or that the email provider refuses to send to, is not invited.
- If invites cannot be queued, the people are still created as pending invites and can be sent their invite with Resend invite.
- More than 500 people at once is refused.
- Invites cannot make anyone an Owner.
