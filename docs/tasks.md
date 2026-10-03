# Task ledger

Owners are current research contributors or proposed future responsibilities, not permanently running agents. Estimates are deliberately omitted until hardware and scope are confirmed.

| ID / requirement | Owner | Dependencies | State | Output/evidence | Review/QA | Next action |
| --- | --- | --- | --- | --- | --- | --- |
| T01 / all | Main agent | Pasted advice | Research complete | research.md; official webpages | Source review collected | Define import fidelity fixtures |
| T02 / R03,R06,R07 | Controller researcher | Primary docs/repos | Research complete | Corrections and hardware gates | Unknown actual board retained | Qualified lab identification |
| T03 / all | Stack researcher | Product goals | Recommendation ready | Rust/TS/Tauri comparison | Windows confirmed; no dependency adoption claimed | Validate actual lab OS/toolchain and team skills |
| T04 / R08 | Main agent | Reference webpage review | Concept checked | design.md, design-concept.html | Desktop browser journeys passed | Maintain prototype boundaries |
| T05 / all | Main agent | Name, GitHub target/visibility confirmed | Created | Public NAVANEETHVVINOD/kerfivo | Remote identity verification pending | Verify and publish reviewed planning package |
| T06 / R01 | Proposed editor owner | Confirmed scope; T05 | Planned | Versioned document + import/edit/save | Unit + actual save/reopen E2E | Define fidelity fixtures then implement |
| T07 / R02,R03 | Proposed Rust core owner | T06; confirmed bed/origin | Planned | Operations, containment, offsets, raster and preview | Geometry invariants + sample journeys | Prototype normalized document pipeline |
| T08 / R04 | Main agent + lab staff | Machine/material evidence | Planned | Approved materials and recipe revisions | Coupon results on exact machine | Define recipe and approval workflow |
| T09 / R06,R07 | Proposed adapter owner | T02 hardware evidence; T07 | Blocked by identification | One confirmed-controller adapter | Fixtures; real supervised acceptance | Record board/driver/capabilities |
| T10 / R05,R09,R10 | Proposed library owner | Public/local-first/zero-budget confirmed | Planned | GitHub-backed catalog + licensed files + offline cache | Real download/integrity/offline E2E | Implement catalog schema and reviewed contributions |
| T11 / all | Independent reviewer | T04 and documents | Review completed | verification.md | 12 relative links resolve; stale wording found | Main agent corrected confirmed-scope wording |
| T12 / all | Main agent / QA | Implemented slices | Planned | Current-source local checks and journeys | Required checks must actually pass | Record results before app push |
| T13 / all | Main agent | Authorized push; T12 | Planned | Current-head hosted CI/release evidence | No merge/deploy authorization inferred | Inspect hosted revision after push |

## GitHub implementation tasks

The user authorized public project setup; these issues are real and were created in NAVANEETHVVINOD/kerfivo:

1. [Machine/controller evidence](https://github.com/NAVANEETHVVINOD/kerfivo/issues/1) — blocks live control and exact recipe commissioning.
2. [Windows editor/import/save](https://github.com/NAVANEETHVVINOD/kerfivo/issues/2) — Rust + Vue/TypeScript/Tauri; SVG/DXF/PNG/JPEG essential.
3. [Rust preparation and preview](https://github.com/NAVANEETHVVINOD/kerfivo/issues/3) — depends on normalized document; real bed validation needs #1.
4. [Identified-controller adapter](https://github.com/NAVANEETHVVINOD/kerfivo/issues/4) — depends on #1 and #3; includes real supervised acceptance.
5. [Public local-first catalog client](https://github.com/NAVANEETHVVINOD/kerfivo/issues/5) — real revision download, content checks and offline cache.
6. [Tested materials/recipes](https://github.com/NAVANEETHVVINOD/kerfivo/issues/6) — depends on machine/staff evidence; no universal presets.
7. [Windows QA/review/CI gates](https://github.com/NAVANEETHVVINOD/kerfivo/issues/7) — current-source checks and real acceptance before application pushes.

Research/design and starter asset publication are complete work items; implementation issues remain open. Creating issues does not claim application features are implemented.

## Concrete completion gates

- Repository: selected owner/name/visibility exists; URL and remote identity verified. Documentation-only initialization is separate from an application release.
- Editor: known-scale SVG imports, edit/undo, save/reopen and operation assignment pass real local journeys.
- Preparation: bounds and precedence checks pass; preview accurately represents operation order; relevant edits invalidate prepared job.
- Controller: known board and driver; exact encoder/transport fixtures; supervised laser-disabled motion and approved coupon job; disconnect/abort tested with observed behavior.
- Library: real versioned catalog/file downloads; contribution review and per-asset rights checked; downloaded revision/license/hash retained; cached design reopens offline. No hosted upload/auth service implied by a public catalog.
- Release: current-source checks and required real E2E pass; independent review findings resolved; current-head hosted CI verified. Hardware and service tests cannot be replaced with a simulator and called complete.

## Desktop build and expanded backlog

| Owner | Dependencies | State | Output/evidence | Review/QA result | Next action |
| --- | --- | --- | --- | --- | --- |
| Main agent | Confirmed Windows/local-first scope | Offline source implemented locally | Rust/Tauri + Vue/TypeScript, SQLite, imports and preparation | Frontend build and 15 Rust tests passed before final delta | Rerun latest source; native Windows journeys |
| Read-only reviewer | Current native/frontend source | Two static reviews complete | Geometry/resource and async-state defects identified | Fixes integrated; final delta pending | Inspect fixes and remaining limits |
| Main agent | Official bundler tools | Executable built; installer retry | Debug and optimized Windows exe | Native launch/install unverified | Complete packaging; acceptance |
| Main agent | Official Luban/M2 manuals | Feature issues created | GitHub #8–18, feature-comparison.md and wireframes.md | No parity/release/hardware claims | Implement slices with real acceptance |
| Lab operator + adapter owner | #1 controller evidence | Live control blocked by machine identity | Disabled controls and machine_ready=false | No commands sent | Identify and commission actual board |

Additional real GitHub tasks: [#8 portable projects/recovery](https://github.com/NAVANEETHVVINOD/kerfivo/issues/8), [#9 canvas editing](https://github.com/NAVANEETHVVINOD/kerfivo/issues/9), [#10 import fidelity](https://github.com/NAVANEETHVVINOD/kerfivo/issues/10), [#11 photo editing/tracing](https://github.com/NAVANEETHVVINOD/kerfivo/issues/11), [#12 fill/dot strategies](https://github.com/NAVANEETHVVINOD/kerfivo/issues/12), [#13 kerf/optimization](https://github.com/NAVANEETHVVINOD/kerfivo/issues/13), [#14 preview/preflight](https://github.com/NAVANEETHVVINOD/kerfivo/issues/14), [#15 control lifecycle](https://github.com/NAVANEETHVVINOD/kerfivo/issues/15), [#16 licensed catalog](https://github.com/NAVANEETHVVINOD/kerfivo/issues/16), [#17 guided UI](https://github.com/NAVANEETHVVINOD/kerfivo/issues/17), [#18 Windows packaging/acceptance](https://github.com/NAVANEETHVVINOD/kerfivo/issues/18).
