---
appliesTo:
  - { type: context, context: { place: web::dashboard } }
references:
  - { kind: code, role: implementation, target: "src/lib/stores/auth.ts" }
---

# The dashboard logs out after fifteen minutes of inactivity

After ten minutes without activity the dashboard asks whether the person is still there; after fifteen it logs them out.
