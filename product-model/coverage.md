---
scope: The booking site, client area, staff sign-in, dashboard and server administration of the web app, with the API and services behind them.
method: Static inspection of routes, API handlers, services, schemas, client-side crypto, UI messages and docs; no code was run.
covered:
  - description: Booking site, client login and client appointment pages.
    paths: ["src/routes/(pages)/(clients)/"]
  - description: Server setup, e-mail confirmation, passkey setup, login and logout pages.
    paths: ["src/routes/(pages)/setup/", "src/routes/(pages)/confirm/", "src/routes/(pages)/login/", "src/routes/(pages)/logout/"]
  - description: Dashboard pages for calendar, agents, channels, absences, staff, settings, account and tenants.
    paths: ["src/routes/(pages)/dashboard/"]
  - description: API handlers for tenants, appointments, staff, notifications, authentication and the public booking site.
    paths: [src/routes/api/tenants/, src/routes/api/auth/, src/routes/api/admin/, src/routes/api/me/, src/routes/api/public/]
  - description: Server services, schemas, authorization and e-mail sending.
    paths: [src/lib/server/services/, src/lib/server/db/, src/lib/server/auth/, src/lib/server/utils/, src/lib/server/email/]
  - description: Client-side encryption, browser stores and dashboard layout.
    paths: [src/lib/client/, src/lib/crypto/, src/lib/stores/, src/lib/components/layouts/, src/lib/utils/, src/lib/const/]
  - description: UI messages in English and German.
    paths: [project.inlang/]
exclusions:
  - description: UI component library and page templates.
    paths: [src/lib/components/ui/, src/lib/components/templates/]
  - description: E-mail templates and wording.
    paths: [src/lib/server/email/templates/]
  - description: Central and tenant database migrations.
    paths: [migrations/, tenant-migrations/]
  - description: Deployment, container and CI configuration.
    paths: [Dockerfile, docker-compose.dev.yml, docker-compose.prod.yml, Caddyfile, .github/, secrets/]
  - description: Logging, OpenAPI documentation, health and environment endpoints.
    paths: [src/lib/logger/, src/lib/server/openapi.ts, src/routes/api/docs/, src/routes/api/openapi.json/, src/routes/api/health/, src/routes/api/log/, src/routes/api/env/]
  - description: Local-only e-mail template previews.
    paths: ["src/routes/(local-only)/"]
  - description: End-to-end tests.
    paths: [e2e/]
unmapped:
  - description: Client PIN reset endpoints and service, which no page uses.
    paths: ["src/routes/api/tenants/[id]/clients/pin-reset/", src/lib/server/services/client-pin-reset-service.ts]
  - description: Session listing and revocation endpoints, which no page uses.
    paths: [src/routes/api/auth/sessions/]
  - description: Placeholder page for changing the e-mail address.
    paths: ["src/routes/(pages)/dashboard/account/change-email/"]
  - description: Status-only appointment cancel endpoint and setup-state override endpoint, which no page uses.
    paths: ["src/routes/api/tenants/[id]/appointments/[appointmentId]/cancel/", "src/routes/api/tenants/[id]/setup-state/"]
limitations: []
---

# Coverage
