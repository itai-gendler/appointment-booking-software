---
kind: edge
routes:
  web: Web
steps:
  - text: Ten minutes pass without activity in the dashboard
    kind: condition
    unattended: true
    entities: []
    contexts:
      web:
        place: web::dashboard
  - text: The Product asks whether the person is still there
    kind: product
    entities: []
    contexts:
      web:
        place: web::dashboard
  - text: Five more minutes pass without an answer
    kind: condition
    entities: []
    contexts:
      web:
        place: web::dashboard
  - text: The Product ends the session
    kind: product
    entities: []
    contexts:
      web:
        place: web::dashboard
---

# Log out after inactivity

## Trigger

Nobody has used an open dashboard for ten minutes.

## Outcome

The person is asked whether they are still there and, without an answer, is logged out after fifteen minutes in all.

## Edge cases

- Answering I am still here keeps the session going.
