---
kind: primary
routes:
  web: Web
steps:
  - text: "The Staff member enters the colleague's name, e-mail address, language and role, and adds the member"
    kind: actor
    actor: staff-member
    entities:
      - { entity: member, effect: reads, facts: [] }
    contexts:
      web:
        place: web::dashboard::staff
  - text: The Product creates the invited Account and Member and e-mails the invitation
    kind: product
    actor: staff-member
    entities:
      - { entity: account, effect: creates, to: Invited, facts: [Name, E-mail address, E-mail language] }
      - { entity: member, effect: creates, facts: [Role, Access] }
    contexts:
      web:
        place: web::dashboard::staff
---

# Invite a staff member

## Trigger

A new colleague needs to manage appointments.

## Outcome

The colleague is listed as invited and can't see appointments yet; an invitation link is in their inbox.
