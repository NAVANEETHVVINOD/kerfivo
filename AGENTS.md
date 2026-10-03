# Kerfivo project guidance

Preserve unrelated user work and keep secrets out of source, logs and issues.
Read docs/README.md and docs/requirements.md for confirmed scope and open machine facts.
Keep narrative project records under docs/; retain required entry files at their expected locations.

Use Rust for the native domain/controller core and TypeScript/Vue for editor/library UI within Tauri. Keep imports and public catalog content untrusted. Original project code/docs are MIT; assets retain separate licenses. Do not copy GPL/AGPL code into MIT code without an explicit compatible licensing decision.

The actual controller, working area and power-control method are unknown. Do not silently identify M2, Ruida or any other board. No real-machine command implementation may claim validated control without board/driver evidence, encoder verification and supervised commissioning. Never bypass physical interlocks or claim exact power-loss resume without evidence.

For substantial independent questions, use narrow read-only subagents; the coordinator owns integration. Record evidence and next actions in docs/tasks.md. Do not recursively delegate by default.

Before application/feature pushes, actual current-source local checks and critical E2E journeys must pass. Do not substitute mocked services for required live verification. Use independent review; before merge verify current head and required checks. A design prototype is not a production application release. No merge, deploy or remote-settings change is implicitly authorized.
