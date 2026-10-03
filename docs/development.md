# Desktop implementation record

The user explicitly requested continuing a real Windows desktop application overnight. Current project root is C:/Users/PC/OneDrive/Documents/ChatGPT/Epilog laser; that directory name does not identify the machine. The MB machine's actual board/bed/power method remain unknown.

Stack: Rust + Tauri 2, Vue 3 + TypeScript + Vite, SQLite. Local files/projects are private by default. Real machine commands stay unavailable until hardware evidence and commissioning. A browser preview of the UI is not equivalent to native desktop acceptance.

Bootstrap tool: official create-tauri-app 4.7.4, npm integrity sha512-7ZXpBxtl+eA3/ZFHWRbp+PpVxU78bpEqOJYa36Jw3mbgXq6GfsGAqDGtK5fEPHGtYwAjkFEDti4VHCauwEC4xg==, upstream tag create-tauri-app-v4.7.4 at dd7f131abca04be596ca38e1377dbceba4742148. Template created in ignored work/tauri-seed; framework files were copied individually into the previously empty project, preserving the earlier planning package.

Rust toolchain exists at C:/Users/PC/.cargo/bin; the bootstrap tool's missing-Rust warning was a PATH issue. Rust/cargo report version 1.94.1. Frontend package versions are explicit; lockfiles record resolved transitive dependencies. Native library versions are deliberate and Cargo.lock will pin them.

An hourly thread heartbeat named “Continue Kerfivo desktop build” is active for the requested overnight continuation. It should notify only for meaningful progress requiring attention, completion, or failure; pause it when the requested outcome is completed. It cannot guarantee uninterrupted execution if the host/app is asleep or disconnected.

## Current implementation checkpoint

Local source now includes the original monochrome Vue desktop UI; native SQLite project save/list/load; bounded plain-outline SVG, visible 2D DXF subset and PNG/JPEG imports; brightness/contrast/invert and threshold/Floyd/Bayer processing; binary raster scan preparation; vector operations, nested cut ordering, passes, workpiece bounds and review warnings. Text outlines are normalized through the same Rust routine used by preparation. Machine readiness is always false.

Completed evidence: frontend production build/typecheck; 9 Rust unit tests plus 7 native-core integration journeys (SQLite save/close/reopen/prepare, explicit DXF units, hidden SVG, collinear curve reversals, empty enabled output, raster inversion). The normalized-text extent regression also passed in the current 16-test run. Browser journeys inspected shape creation, duplicate/undo/redo, both home themes and disabled hardware controls. These are browser UI and native-core checks, not native-window E2E.

Independent static review identified and prompted fixes for curve flattening, hidden geometry, DXF plane metadata, repeat-memory limits, bounded containment, empty output, stale async preparation/image results and mismatched text sizing. Final delta review and current-source rerun remain required; self-intersections, kerf, tracing, vector fills and many editor conveniences are still backlog features.

A debug executable and optimized executable were built at this checkpoint. Two NSIS attempts timed out downloading the official tool. The exact official 3.11 archive and Tauri utils 0.5.3 plugin were then fetched and verified against the hashes in Tauri CLI 2.12.1 source commit 30da1fd6e17de6107ecc850c95dfb16b5729f2dd. Packaging uses the task-local build-tool cache and is pending final output. Executables remain unsigned and native-window launch/install journeys are unverified. No hardware commands, driver changes or paid services were performed.

C drive initially ran out of build space. Generated artifacts were relocated to this task's dedicated D:/CodexBuilds/kerfivo-2026-10-04-native/target and TEMP directory. Some owned generated C target fragments remain; subsequent builds use D without recursive cleanup. No user source was removed. Use the same CARGO_TARGET_DIR for future cargo/Tauri runs.

GitHub now has issues #1–18. Initial public source publication must remain documentation/catalog only until required current-source native desktop acceptance passes. The active heartbeat should continue local editor/packaging/testing work, preserve unknown-hardware gates and report actual blockers rather than pretending the complete machine-control outcome is achieved.
