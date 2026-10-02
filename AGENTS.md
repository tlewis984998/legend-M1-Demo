# Agent rules for this repo
- Java 17 work is limited to examples/service-execution-jar/** plus any
  GitHub Actions workflow or docs file the task explicitly names.
- Never upgrade Legend Engine/SDLC versions without a reproducible
  Java 17 failure that proves it is required. Include the evidence.
- Security or dependency findings outside the task scope: open a
  follow-up issue; do not fix them in the same PR.
- Every PR includes before/after build output and a rollback note.
