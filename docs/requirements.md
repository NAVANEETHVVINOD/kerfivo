# Requirements and unresolved decisions

Confirmed outcome: a Windows desktop replacement workflow for editing, engraving/cutting and local USB control, plus an open-source public design library that anyone can browse/contribute to and run locally. Budget: zero paid hosting. Essential imports: SVG, DXF and PNG/JPEG. Public GitHub owner: NAVANEETHVVINOD. Selected name: Kerfivo. The user reports MB CO2, 100 W, CorelDRAW 12/CorelLaser; actual board/bed/power method remain unresolved.

## Proposed acceptance criteria

| ID | Need | Observable acceptance |
| --- | --- | --- |
| R01 | Accurate editing | Import an SVG with known dimensions; preserve scale in millimetres; edit position/size/text with undo/redo; save/reopen without geometric change. |
| R02 | Engrave and cut together | One project assigns explicit engrave/score/cut operations and produces an inspectable ordered job; inner closed cuts precede enclosing cuts. Hardware execution is verified on the identified controller. |
| R03 | Clear origin setup | Display bed coordinates, job anchor and coordinate trust separately; preview the job footprint; refuse out-of-bounds jobs. |
| R04 | Material guidance | Show machine-specific tested recipes and their source/date/approver; distinguish manual power instructions and reference settings. No invented production presets. |
| R05 | Online design library | Public browsing, reviewed contributions, search/filter, dimensions/author/license/revision and actual asset download; reopen a cached asset offline. Initial model uses GitHub contributions without a separate app account. |
| R06 | Honest machine control | Only supported controls are available; connection, busy, acknowledged transfer and completion are separate states; software stop latency is measured. |
| R07 | Interruption handling | Persist the prepared job and host log; on uncertain execution or power loss invalidate position and offer an explicit recovery process. Exact auto-resume is excluded until demonstrated. |
| R08 | Lab usability | A new user can prepare a named sample through design, operations and preview without consulting protocol controls. Staff commissioning/admin tasks use separate flows. |
| R09 | Local-first operation | Editing, local projects and validated recipes work without the online library; synchronization failure does not block local editing. |
| R10 | Library content isolation | Reject unsafe/oversized SVGs and external-resource imports; opening library content cannot execute scripts or machine commands. |

These are proposed targets, not completed functionality. Numeric tolerances, performance targets and confirmed test materials are to be agreed using the actual machine and lab workload.

## Questions already sent

1. Name criteria answered: short, modern, discoverable and domain candidates without registration records. Kerfivo selected after research.
2. GitHub answered: public under NAVANEETHVVINOD.
3. Platform answered: Windows desktop editor and local USB, plus online design library.
4. Machine answered: board/bed/power method unknown; 100 W user-reported. Needs physical evidence.
5. Library answered: anyone can browse/contribute, open source, free and locally runnable.
6. Imports answered: SVG, PNG/JPEG and DXF are V1 essentials.

## Focused next batch after those answers

- Who operates the laser: students, trained staff, or both? Who approves materials and published assets?
- Keep the existing board, or is a qualified hardware upgrade within scope? No upgrade purchase is recommended before identification.
- Define the supported DXF subset and handling of splines, units, blocks and text; PDF/native CDR are not currently V1 requirements.
- Library proposal: public GitHub catalog with pull-request contributions and per-asset licenses, local browsing and optional download/sync. This needs no paid host or separate production login service.
- Original code/docs use MIT as the initial open-source license; third-party content retains its own license and attribution. License review is required before external code reuse.
- Preferred languages/UI conventions and the team's skills? Camera alignment, rotary, nesting, batch jobs and generator templates are later candidates, not assumed V1 commitments.

Machine evidence should come from existing software settings, nameplate and qualified staff inventory. Do not open energized electrical compartments to gather it. USB VID/PID is supporting evidence, not a unique controller identity.

## Proposed delivery slices

1. Research, confirmed scope, original design and repository.
2. Desktop editor, local save/reopen and operation preview. No implied live controller integration.
3. Identified-controller integration: source fixtures, laser-disabled motion and supervised acceptance jobs.
4. Public GitHub-backed design catalog, real asset downloads and local cache; pull requests review contributions. A fully hosted upload service is a later option, not a zero-budget prerequisite.
5. Tested recipes, calibration tools, generators/nesting/camera features as separate validated increments.

The ordering minimizes rework; it does not drop the requested online library or machine control from the intended outcome.
