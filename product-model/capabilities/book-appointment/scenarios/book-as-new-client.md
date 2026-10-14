---
kind: primary
routes:
  web: Web
steps:
  - text: The Client chooses to book on the home page
    kind: actor
    actor: client
    entities: []
    contexts:
      web:
        place: web::booking-site::home
  - text: The Client selects an appointment type
    kind: actor
    actor: client
    entities:
      - { entity: channel, effect: reads, facts: [Name, Description] }
      - { entity: appointment, effect: reads, facts: [] }
    contexts:
      web:
        place: web::booking-site::book-appointment
  - text: "The Client selects an agent, or No preference"
    kind: actor
    actor: client
    entities:
      - { entity: agent, effect: reads, facts: [Name, Description, Image] }
    contexts:
      web:
        place: web::booking-site::book-appointment
  - text: The Client selects a day and one of its free slots
    kind: actor
    actor: client
    entities: []
    contexts:
      web:
        place: web::booking-site::book-appointment
  - text: "The Client adds their name, e-mail address and phone number, and chooses whether to be notified by e-mail"
    kind: actor
    actor: client
    entities: []
    contexts:
      web:
        place: web::booking-site::book-appointment
  - text: "The Client chooses It's my first time here and sets a six-digit PIN"
    kind: actor
    actor: client
    entities: []
    contexts:
      web:
        place: web::booking-site::book-appointment
  - text: The Client reviews the summary and chooses Book appointment
    kind: actor
    actor: client
    entities:
      - { entity: appointment, effect: reads, facts: [] }
    contexts:
      web:
        place: web::booking-site::book-appointment
  - text: "The Product creates the Client's account at this tenant, protected by the PIN"
    kind: product
    actor: client
    entities:
      - { entity: client, effect: creates, facts: [E-mail address, PIN] }
      - { entity: account, effect: reads, facts: [] }
      - { entity: tenant, effect: reads, facts: [] }
    contexts:
      web:
        place: web::booking-site::book-appointment
  - text: "The Product books the Appointment, encrypted for the Client and every staff member with access"
    kind: product
    actor: client
    entities:
      - { entity: appointment, effect: creates, to: Confirmed, facts: [Date and time, Duration, Time zone, Name, E-mail address, Phone number, Language, E-mail updates, Progress, Booked at] }
      - { entity: staff-member, effect: reads, facts: [] }
    contexts:
      web:
        place: web::booking-site::book-appointment
  - text: The Product e-mails the booking details with a link to cancel when the Client asked to be notified
    kind: product
    actor: client
    entities:
      - { entity: appointment, effect: reads, facts: [Date and time, E-mail address, Language, E-mail updates] }
    contexts:
      web:
        place: web::booking-site::book-appointment
  - text: The page confirms the booking and offers to add it to a calendar or book another
    kind: condition
    entities: []
    contexts:
      web:
        place: web::booking-site::book-appointment
---

# Book as a new client

## Trigger

Someone books with this tenant for the first time.

## Outcome

The client has an account protected by their PIN and a booked appointment; they get the details by e-mail if they asked to be notified.

## Decision points

### Whom is the appointment with?

Did the client pick an agent?

- An agent was picked → only that agent's free slots are offered, and the appointment is with them.
- No preference → every agent's free slots are offered, and the appointment is with the first agent free in the chosen slot.

## Edge cases

- A phone number is required when the tenant requires one.
- A PIN that is too easy to guess is refused.
