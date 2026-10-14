---
kind: primary
routes:
  web: Web
steps:
  - text: The tab is missing the keys to read client details
    kind: condition
    entities:
      - { entity: client, effect: reads, facts: [] }
    contexts:
      web:
        place: web::dashboard
  - text: The Staff member loads the keys with their passkey
    kind: actor
    actor: staff-member
    entities:
      - { entity: passkey, effect: reads, facts: [] }
    contexts:
      web:
        place: web::dashboard
  - text: The Product unlocks the encryption keys of the Passkey for this tab
    kind: product
    actor: staff-member
    entities:
      - { entity: passkey, effect: reads, facts: [] }
    contexts:
      web:
        place: web::dashboard
---

# Load the keys with a passkey

## Trigger

A staff member opens the dashboard in a tab that lacks their cryptography keys.

## Outcome

Client details can be read and added in this tab.

## Edge cases

- Choosing I just want to change settings closes the prompt; client details stay locked in that tab.
