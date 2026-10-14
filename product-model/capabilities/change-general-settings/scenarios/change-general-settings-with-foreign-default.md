---
kind: validation
routes:
  web: Web
steps:
  - text: The Staff member selects languages and a default language outside them
    kind: actor
    actor: staff-member
    entities: []
    contexts:
      web:
        place: web::dashboard::general-settings
  - text: "The default language is not among the languages, so the Product refuses"
    kind: condition
    entities: []
    contexts:
      web:
        place: web::dashboard::general-settings
---

# Choose a default language that is not offered

## Trigger

A tenant admin picks a default language outside the selected languages.

## Outcome

Nothing is saved; the form says the default language must be one of the selected ones.
