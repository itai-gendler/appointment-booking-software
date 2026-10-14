---
relations:
  - { entity: passkey, verb: has, cardinality: one-to-many }
references:
  - { kind: code, role: implementation, target: "src/lib/server/db/central-schema.ts#user" }
  - { kind: code, role: implementation, target: "src/lib/server/db/central-schema.ts#userInvite" }
---

# Account

The sign-in identity of a global admin or a staff member, and what belongs to
the person whatever their role.

## Information kept

- **Name** — the person's name, 2 to 50 characters
- **E-mail address** — the address they sign in with and receive e-mails at; unique on this server
- **E-mail language** — English or German, the language OpenReception writes to them in
- **Passphrase** — an optional passphrase of at least 30 characters, a backup way for a global admin to sign in

## States

### Invited

Created, and waiting for the person to confirm their e-mail address through the emailed link.

### Confirmed

E-mail address confirmed; the person can set up a passkey and sign in.
