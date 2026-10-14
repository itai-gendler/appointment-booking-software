---
kind: primary
routes:
  web: Web
steps:
  - text: "The Staff member picks a retention period and turns the phone number requirement on or off, and saves"
    kind: actor
    actor: staff-member
    entities: []
    contexts:
      web:
        place: web::dashboard::advanced-settings
  - text: "The Product saves the Tenant's advanced settings"
    kind: product
    actor: staff-member
    entities:
      - { entity: tenant, effect: changes, facts: [Appointment retention, Phone number required] }
    contexts:
      web:
        place: web::dashboard::advanced-settings
---

# Change retention and phone requirement

## Trigger

A tenant admin aligns the tenant with its data protection rules.

## Outcome

Appointments are deleted after the chosen period, and booking asks for a phone number if required.

## Edge cases

- Saving these during onboarding completes the settings step, as saving the address does.
