---
relations:
  - { entity: member, verb: has, cardinality: one-to-many }
  - { entity: agent, verb: has, cardinality: one-to-many }
  - { entity: channel, verb: has, cardinality: one-to-many }
  - { entity: client, verb: has, cardinality: one-to-many }
references:
  - { kind: code, role: implementation, target: "src/lib/server/db/central-schema.ts#tenant" }
  - { kind: code, role: implementation, target: "src/lib/server/services/tenant-admin-service.ts#TenantAdminService" }
  - { kind: code, role: implementation, target: "src/lib/const/tenants.ts" }
---

# Tenant

An organization or individual collecting appointments on this server, with
its own domain, booking site, staff, agents and channels. Everything a tenant's
clients book stays inside that tenant.

## Information kept

- **Short name** — a unique name on this server of 4 to 15 characters that cannot start or end with a dash; it cannot be changed once the tenant is added
- **Domain** — the address its booking site and dashboard are reached at; unique on this server
- **Name** — the public name of the organization
- **Description** — a short description shown on the home page, kept per language
- **Logo** — an optional image shown on the home page
- **Languages** — the languages its clients see; at least one
- **Default language** — the language shown to clients whose own language is not offered; one of the Languages
- **Visitor address** — street, number, additional address info, ZIP code and city, included in appointment information for clients
- **Website** — an optional link shown on the home page
- **Imprint** — an optional link shown in the footer
- **Privacy statement** — an optional link shown in the footer
- **Appointment retention** — after how many days past their date appointments are deleted: 30, 60, 90, 180 or 365; 30 for a new tenant
- **Phone number required** — whether clients must give a phone number when booking; off for a new tenant

## States

### Awaiting settings

Just added; its settings have not been saved yet. The booking site says it is not ready to accept appointments.

### Awaiting agents

Settings saved; no agent exists yet.

### Awaiting channel

Agents exist, but no active channel has both an agent and a schedule.

### Awaiting staff

A complete channel exists, but no staff member has joined the tenant yet.

### Ready

Fully set up: the booking site offers its channels to clients.
