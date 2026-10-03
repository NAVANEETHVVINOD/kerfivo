# Research findings

Reviewed 4 October 2026 using primary project repositories, official product documentation and supplier listings. Current branches/webpages can change; immutable reference snapshots are listed separately when available. No dependency has been installed or adopted in an application.

## What we know about the lab

The user reports difficult editing, configuration, origin positioning, combined engraving/cutting and library access in a legacy CorelDRAW 12/CorelLaser workflow. They want a modern custom application, favor Rust, and request research, design, tasks and a new GitHub repository.

The user reports an MB-labelled enclosed CO2 machine with a 100 W rating. No actual photograph, nameplate, board marking, USB inventory or working area measurement was supplied in this chat. The 100 W rating is user-reported and awaits label verification; exact manufacturer, model, bed size and controller remain unverified.

Motivate Box lists MB6090 100 W and MB1390 products. That establishes plausible supplier/model candidates, not that the lab owns either configuration. A current listing cannot establish how an older machine was built. [Supplier product page](https://www.motivatebox.in/laser-cutting-machine.html), [supplier catalog](https://www.motivatebox.in/motivate-box.pdf).

## Corrections to the pasted advice

| Earlier claim | Evidence-based treatment |
| --- | --- |
| The machine is definitely M2 Nano | Unconfirmed. Record physical board marking and the existing software's selected mainboard. CorelLaser is a clue. |
| Moshi and M2 are essentially equivalent | Separate protocols/adapters. K40 Whisperer explicitly excludes Moshi. |
| A USB security dongle proves the controller | It does not. K40 Whisperer does not require a dongle for its supported boards. |
| Raw EGV equals 30-byte USB frames | Separate layers: LHYMICRO-GL command language, EGV file metadata, command payload, checksum/status logic and CH341 USB transport. MeerK40t uses 30-byte command payloads, with additional framing. |
| XOR checksum and arbitrary direction characters are sufficient | Do not implement from this shorthand. Review actual CRC, speed encoding, transport and queue/status code; compare exact bytes against known-good fixtures. |
| Software presets replace a stock M2 power dial | M2 provides laser on/off, not programmable laser current. Presets must retain a manual power/current step. Newer M3 behavior is separate and wiring-dependent. |
| Rust translation makes GPL code permissively reusable | Translation does not erase license obligations. Track source provenance and license before reuse. |
| A 2-opt path sorter guarantees holes before outer cuts | Geometric containment produces precedence constraints. Travel optimization must respect those constraints. |
| usvg/resvg automatically solve machining geometry | SVG parsing/rendering is only part of the pipeline. Explicit unit conversion, curve flattening, clipping and operation semantics are still necessary. |
| Kerf is always 0.12 mm | Measure on the exact material/machine/process. Store test conditions and uncertainty. |
| Controller replacement costs $30–$60 installed | Unverified. The researched Mini Gerbil vendor listing was $100 sale/$115 regular, before regional costs and installation; compatibility needs assessment. |
| Power loss can resume at the exact byte/position | Not a justified capability. Queued, acknowledged and physically executed movements are different states. After uncertainty, invalidate position and require supervised recovery. |
| CorelLaser universally cannot combine passes or frequently drops packets | The user's workflow problem is valid; those universal technical explanations were not established by the supplied evidence. Reproduce the local limitation before attributing its cause. |

Primary protocol/board references: [K40 Whisperer official page](https://www.scorchworks.com/K40whisperer/k40whisperer.html), [MeerK40t LHYMICRO-GL protocol](https://github.com/meerk40t/meerk40t/wiki/Tech:-Lhymicro-Control-Protocols), [M2 hardware](https://github.com/meerk40t/meerk40t/wiki/Tech:-Lhymicro-M2-Nano-Hardware), [Lihuiyu controller source](https://github.com/meerk40t/meerk40t/blob/master/meerk40t/lihuiyu/controller.py), [Lihuiyu driver source](https://github.com/meerk40t/meerk40t/blob/master/meerk40t/lihuiyu/driver.py), [Mini Gerbil vendor](https://awesome.tech/shop/).

## Existing software: practical alternatives and design references

| Product | Useful evidence | Fit for this project |
| --- | --- | --- |
| K40 Whisperer | Lihuiyu-focused raster/vector workflow; supported-board list and troubleshooting | Possible immediate alternative if the actual board is supported. Python/GPL; use official releases after identification. |
| MeerK40t | MIT; wxPython interface; multiple controller families | Strong permissive protocol/operations reference, including Lihuiyu. Current README describes low-maintenance mode; review source and reliability rather than assuming ongoing support. |
| LightBurn | Mature editor, operation settings, preview and libraries | Strong interface benchmark. Official compatibility information excludes M2 Nano; Ruida and supported G-code boards are different cases. |
| Snapmaker Luban | Beginner-oriented edit/process/workspace flow and case library | Useful flow reference, designed for Snapmaker machines. Its G-code output is not an M2 integration. Repository declares AGPL-3.0. |
| FLUX Beam Studio | Integrated design/position/preview experience | Design reference for FLUX systems. Do not use its product name or infer compatibility with MB. |
| Rayforge | MIT; GTK4/Libadwaita; job planning and listed GRBL, Marlin, Ruida, Smoothieware drivers | Useful preparation/driver architecture reference. Its listed compatibility is not evidence of stock M2 support. |

Sources: [MeerK40t](https://github.com/meerk40t/meerk40t), [LightBurn compatibility](https://lightburnsoftware.com/pages/which-version-do-i-need), [Luban repository](https://github.com/Snapmaker/Luban), [Luban laser workflow](https://wiki.snapmaker.com/en/Snapmaker_Luban/manual/configure_%26_generate_3axis_laser_gcodes_using_luban), [FLUX](https://flux3dp.com/beam-studio/), [Rayforge](https://github.com/barebaric/rayforge).

## Recommended languages

**Recommend Rust + TypeScript, with SQL for storage.** Rust owns normalized geometry, toolpath preparation, validation, persistence and controller adapters. TypeScript owns Vue components, editor interaction and shared web-library UI. Keep SQL migrations versioned. This is a reasoned recommendation for these needs, not a universal performance guarantee.

| Option | Benefits | Costs / decision |
| --- | --- | --- |
| Rust + Tauri 2 + Vue 3/TypeScript/Vite | Rust native core; web UI can share library components; strong types across contracts | IPC and two-language boundary need discipline. Best proposed long-term fit. |
| Python + Qt/wxPython | Existing laser ecosystem; quick experiments and tooling | Packaging and UI/library reuse require separate work. Best for a diagnostic/reference harness or extending an existing product. |
| Rust + egui | One main implementation language; direct native interaction | Reusing an online library UI is less straightforward; editor interaction still substantial. Good alternative if an all-Rust desktop is a firm requirement. |
| Browser-only TypeScript | Easy distribution for browsing/editing library assets | Browser USB support/driver/platform constraints make it an unsuitable default for this unknown legacy controller. Retain desktop authority for machine actions. |
| C++ + Qt | Mature native desktop/editor tooling | Higher memory-management and build complexity for a new small-team app. Viable if the team already uses it. |

Tauri officially supports frontend frameworks but recommends Vite-based SPAs and does not natively support SSR. **Nuxt is optional; use Vue/Vite for desktop unless there is a confirmed need for it.** A separate public website can later use SSR if discovery/SEO requirements justify it. [Tauri frontend guidance](https://v2.tauri.app/start/frontend/).

Candidate dependencies: usvg/resvg for SVG normalization/rendering, svgtypes for parsing primitives, image for image processing, cavalier_contours for applicable polyline offsets, SQLite/rusqlite for local data, and nusb or rusb after Windows driver investigation. None is a turnkey editor or universal geometry solution. Benchmark large SVGs and offset edge cases; contain failures at job preparation boundaries.

Windows USB is a selection gate: nusb requires a WinUSB-associated device/interface. Replacing a legacy driver can affect CorelLaser. Inventory and preserve the working driver before any change; USB enumeration alone does not prove a board's protocol. rusb wraps libusb, so distribution must consider the wrapper and libusb licenses separately. [nusb](https://github.com/kevinmehall/nusb), [rusb](https://github.com/a1ien/rusb), [libusb licensing](https://libusb.info/), [resvg](https://github.com/linebender/resvg), [cavalier_contours](https://github.com/jbuckmccready/cavalier_contours).

Use exact reviewed versions, Cargo/npm lockfiles and immutable source revisions during implementation. Do not copy the pasted dependency/version list directly.

DXF is confirmed essential for V1. Evaluate [ixmilia/dxf-rs](https://github.com/ixmilia/dxf-rs) and its [Drawing API](https://docs.rs/dxf/latest/dxf/struct.Drawing.html) as a parser candidate, then normalize the supported entities into the same millimetre model. Test explicit units, unitless files, lines/arcs/circles/polylines, blocks/transforms, splines and text. Show unsupported entities; never silently omit them. This is an evaluation candidate, not an adopted pinned dependency. The project's documented converter-based interop tests have an external ODA tool prerequisite, so do not claim those run without that tool.

## Immutable research snapshots

The following were inspected by the stack researcher; these are reference snapshots, not installed/adopted dependencies:

- [nusb manifest](https://github.com/kevinmehall/nusb/blob/58b056f4d8fe37335ea1571d4a666779e1cfc32e/Cargo.toml): inspected version 0.2.7; Rust minimum 1.85. [Windows requirements](https://docs.rs/nusb/latest/nusb/#windows).
- [usvg manifest](https://github.com/linebender/resvg/blob/1fe3cfe88bc692612f1ccd4403ba3476b2cdd813/crates/usvg/Cargo.toml): inspected version 0.48.1; manifest requires Rust 1.85 despite a stale older README badge.
- [Cavalier manifest](https://github.com/jbuckmccready/cavalier_contours/blob/22887a824d22cd8ab50968a551f34cdb4508127f/Cargo.toml): inspected version 0.9.0; Rust minimum 1.88. Its [README](https://github.com/jbuckmccready/cavalier_contours/blob/22887a824d22cd8ab50968a551f34cdb4508127f/README.md) warns of possible panics for bad inputs/bugs.
- [MeerK40t README](https://github.com/meerk40t/meerk40t/blob/d511944e08788e88077727f682957759884ff5ca/README.md) and [MIT license](https://github.com/meerk40t/meerk40t/blob/d511944e08788e88077727f682957759884ff5ca/LICENSE).
- [Rayforge README](https://github.com/barebaric/rayforge/blob/77b668c1a1dbbd7ae4bd83d0255aeff515d2d8f3/README.md) and [MIT license](https://github.com/barebaric/rayforge/blob/77b668c1a1dbbd7ae4bd83d0255aeff515d2d8f3/LICENSE).

## Naming

Selected **Kerfivo**, pronounced ker-fee-vo, with descriptor **Laser Design & Control**. It connects cutting terminology to a short distinctive product name. The user requested a discoverable modern name and authorized a public repo under NAVANEETHVVINOD. No exact-name web result or GitHub repository was found in the research check; this is a narrow search result, not worldwide trademark clearance or an SEO ranking guarantee.

Authoritative registry lookups on 4 October 2026 returned HTTP 404 for [kerfivo.com](https://rdap.verisign.com/com/v1/domain/kerfivo.com) and [kerfivo.app](https://pubapi.registry.google/rdap/domain/kerfivo.app). This means no registration record was returned then. Registrar availability, premium pricing and future availability are not guaranteed. No domain purchased/reserved. [GitHub name search](https://api.github.com/search/repositories?q=kerfivo%20in%3Aname).

Alternatives Kerfyo and Kerfzy also had no returned .com/.app registration records in the research pass. Kerfli was rejected because an existing cutting-planner app uses it; Kerflo/Lazivo/Lazuno have existing brand uses. BeamStudio Lab was withdrawn because FLUX already has Beam Studio. A coined name plus descriptive titles/content supports discoverability; do not claim that a name alone guarantees SEO.
