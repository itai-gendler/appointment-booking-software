---
appliesTo:
  - { type: entity, id: tenant, effect: changes, facts: [Name, Description, Logo, Languages, Default language, Visitor address, Website, Imprint, Privacy statement, Appointment retention, Phone number required] }
permits:
  - actors: [global-admin]
  - related: [{ verb: has, entity: member }, { verb: holds, entity: staff-member }]
    when:
      - { entity: member, fact: Role, is: Tenant Admin }
references:
  - { kind: code, role: implementation, target: "src/lib/server/utils/permissions.ts#checkPermission" }
  - { kind: code, role: implementation, target: "src/routes/(pages)/dashboard/staff/(components)/utils.ts" }
---

# Only tenant admins and global admins change a tenant's settings

A tenant's name, description, logo, languages, address, links and advanced settings are changed by its tenant admins, or by a global admin managing it.
