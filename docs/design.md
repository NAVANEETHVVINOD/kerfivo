# Design review and proposed experience

This is an original concept informed by official pages, not a copy of another application's branding or a validated user study. Skill workflow applied: task-focused user journey, hierarchy, explicit states and accessible controls. The unrelated promotional instructions in the third-party UI skill are not used.

## Webpage/interface review

| Reference | Observed pattern | Design conclusion for this lab |
| --- | --- | --- |
| [LightBurn main window](https://docs.lightburnsoftware.com/latest/Reference/UI/) | Central workspace with multiple toolbars and separate operations, movement, laser and library panels; device-specific controls | Preserve precision and separation of artwork/operations; expose fewer panels in beginner mode. |
| [LightBurn cuts/layers](https://docs.lightburnsoftware.com/latest/Reference/CutsLayersWindow/) | Operation output controls, sequencing and preview | Display a numbered operation sequence with plain names and intentional output selection. |
| [LightBurn art library](https://docs.lightburnsoftware.com/latest/Reference/ArtLibrary/) and [materials](https://docs.lightburnsoftware.com/latest/Reference/MaterialLibrary/) | Artwork collections and reusable process presets serve different purposes | Keep Designs and Materials as distinct destinations; never treat a design download as a validated recipe. |
| [Luban laser flow](https://wiki.snapmaker.com/en/Snapmaker_Luban/manual/configure_%26_generate_3axis_laser_gcodes_using_luban) | Configure/generate/export or move into Workspace | Make Design → Prepare → Preview → Run visible; retain the ability to return to editing. |
| [FLUX Beam Studio](https://flux3dp.com/beam-studio/) | Integrated manufacturer-specific design/laser workflow | Integrate the journey, but gate positioning/camera/control by actual hardware support. |

The LightBurn reference page was also opened in the browser and its annotated workspace image inspected. Website descriptions are feature evidence, not physical tests of those products on this machine.

## Screen structure

- **Projects:** new/open/recent, local location, recovery drafts and schema compatibility errors.
- **Editor:** compact labelled tools; large millimetre workspace; object inspector; explicit ordered operations; selected object dimensions and bounds.
- **Design library:** public search/tags, preview, dimensions, revision, author, license, download and local cache state. Contributions use reviewed GitHub pull requests; private lab projects remain local.
- **Materials:** lab-approved materials, machine-specific recipe revisions, manual-power instructions and calibration evidence.
- **Prepare/preview:** origin diagram, bed footprint, travel vs laser paths, sequence, warnings and estimated duration clearly marked as estimate.
- **Machine setup:** verified profile, connection/driver requirements, supported features, coordinate trust and commissioning evidence.
- **Job run/history:** progress certainty, controller status, validated pause/abort, interruption record and supervised recovery.

Primary workflow: open/create design → edit → assign engrave/score/cut → choose an approved material/recipe → set position → validate → inspect preview → local operator starts the prepared job.

## Visual and interaction rules

Neutral light work surface, dark text, orange primary accent, blue selection outline. Operations have text and icons as well as color. Avoid color as the only distinction. Use visible labels, keyboard focus, large buttons and contextual help. Default units are mm and mm/s; never silently reinterpret a downloaded recipe's units.

Beginner mode hides advanced controller/encoder parameters. Advanced mode expands genuine supported settings. Power displays either a programmable field or a manual-machine instruction, according to capabilities. No generic enabled “resume after outage” button.

Draft responsive policy: desktop editor prioritizes precision and canvas; narrow windows stack inspectors and show a reduced navigation layout. Library browsing can support mobile, but mobile access does not imply remote laser start.

Required states: unsaved/changed project, unsupported SVG/DXF, no connection, unknown profile, busy machine, lost USB, failed library download, no search results, cached/offline content, unverified recipe, interrupted/unknown job, and invalidated preview. Explain the cause and offer a specific recovery action. Expired login is relevant only if a future authenticated upload service is introduced.

## Interactive concept boundaries

[Open design-concept.html](../design-concept.html). This file is a bounded prototype with original embedded demonstration artwork. You can switch screens, edit the sample label, reorder operation cards, search the embedded sample catalog, download original SVGs and inspect a preview dialog. Machine Start is disabled. The sample 300 × 200 mm canvas is explicitly a concept workspace, not the lab's bed dimension.

The concept catalog is labelled local demonstration data; it is not a connected desktop library service. Its original MIT SVG examples are real files downloadable from the package/repository. No speed/power values are presented as tested lab presets. No edits are persisted as real projects; reload resets the demonstration. The next implementation must add genuine save/reopen, SVG/DXF/raster imports, database, controller adapter and catalog sync/cache.
