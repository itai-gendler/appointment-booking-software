---
kind: primary
routes:
  web: Web
steps:
  - text: The Staff member opens the link from the invitation and claims the account
    kind: actor
    actor: staff-member
    entities:
      - { entity: account, effect: reads, facts: [] }
    contexts:
      web:
        place: web::staff-sign-in::email-verification
  - text: The Product confirms the e-mail address of the Account
    kind: product
    actor: staff-member
    entities:
      - { entity: account, effect: changes, from: Invited, to: Confirmed, facts: [] }
    contexts:
      web:
        place: web::staff-sign-in::email-verification
  - text: The page offers Setup Passkey as the next step
    kind: condition
    entities:
      - { entity: passkey, effect: reads, facts: [] }
    contexts:
      web:
        place: web::staff-sign-in::email-verification
---

# Confirm an invitation

## Trigger

A staff member opens the link from their invitation e-mail.

## Outcome

The account is confirmed and the staff member is asked to set up a passkey; they cannot see appointments until they are granted access.
