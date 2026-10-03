# Laser workflow reference and feature backlog

Scope: laser-design/preparation workflows, not Luban's CNC/3D-printing modules and not every historical CorelLaser build. These are independently written features, not translated AGPL/GPL source. Reviewed 4 October 2026. The installed CorelLaser version and actual controller remain unknown.

## Reference evidence

[Luban laser generator manual](https://support.snapmaker.com/hc/en-us/articles/4404753371415-4-Laser-G-code-Generator) documents project setup, imports, drawing, transforms, image conversion, toolpaths and preview. It supports SVG/DXF/PNG/JPEG/BMP, workpiece size/origin, shapes/text, undo/redo, layer order, contrast/brightness/invert/threshold, multiple dithering algorithms, tracing and halftone. Toolpath choices include outlines/fills, line/dot movement, spacing, speed and power. Camera and rotary workflows depend on Snapmaker hardware. This motivates a guided editor; it does not establish MB machine compatibility.

[Luban workspace manual](https://support.snapmaker.com/hc/en-us/articles/4403902804887-6-Workspace) is the reference for transfer/connection and positioning flow. Native head-control capabilities must come from an identified adapter rather than copied Snapmaker assumptions.

[Lihuiyu-branded M2 software manual](https://www.focuslasermachine.com/wp-content/uploads/2020/10/M2-Software-Users-Manual.pdf), supplier-hosted translation, documents raster engraving, vector cutting and vector marking (PDF pp16–17), mechanical/page origins and anchors (pp4–6,18–23), page/selection export (p45), repetition (pp30–31), and grouped engrave/cut tasks (pp47–50). It describes intensity as reserved/inactive for the covered board. Therefore CorelLaser must not be described as universally unable to combine jobs or as providing working software current control. Installed-version behavior needs direct verification.

## Current implementation versus remaining work

| Feature group | Current local desktop source | Remaining acceptance / work |
| --- | --- | --- |
| Guided navigation | Home, Projects, Library, Materials, Settings; Setup → Design → Process → Preview → Position | Unsaved-navigation guard, recovery, keyboard acceptance |
| Appearance | Original monochrome doodle, light/dark, optional red | Contrast/focus review and reduced-motion policy |
| Document | Native SQLite save/list/load and revisioned objects/operations | Portable export/open, backup/recovery, folders |
| Drawing | Rectangle, circle, line, text; numeric position/size/rotation; duplicate/delete/undo/redo | Drag handles, custom paths, grouping, alignment, snapping, mirror |
| Import | Bounded native SVG outline normalization, straight 2D DXF subset, PNG/JPEG | Color/subpath mapping, broader DXF entities, import fidelity fixtures |
| Image editing | Brightness, contrast, invert, threshold/Floyd/Bayer; source retained | Crop, white clip, extra algorithms, tracing, halftone |
| Processing | Raster scan runs, vector score/cut, passes, interval, ordered operations | Vector fills, discrete dot dwell, grayscale capability, kerf, travel optimization |
| Preview | Native paths, containment ordering, workpiece bounds, warnings, invalidation | Timeline, travel overlay, intersections, exact canvas/text parity |
| Library | Three original MIT designs, hash-checked SQLite cache, pinned-commit GitHub fetch code | Real remote publication/sync/offline E2E, license download and moderation |
| Materials | No approved presets; lab fee reference only | Verified machine-specific recipes and coupon workflows |
| Position/run | Disabled control layout, unknown-machine explanation | Board/driver identity, adapter, commissioning, live pause/abort/disconnect behavior |
| Distribution | Debug Windows executable built locally | Installer build, native-window E2E, independent delta review, current CI and signing decision |

Bitmap dithering produces pixel data. Line-fill movement and discrete dot-fill/dwell are separate toolpath choices. A dithered photograph does not automatically use point-dwell movement. The current implementation produces binary raster line scans only.

No claim of exact feature parity, successful physical execution, universal material settings, measured job time, or power-loss recovery is made. Implementation statuses refer to local source, not a published release.
