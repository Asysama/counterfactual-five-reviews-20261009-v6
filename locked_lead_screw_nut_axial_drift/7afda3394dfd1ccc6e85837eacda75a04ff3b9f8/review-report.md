# locked_lead_screw_nut_axial_drift — contributor review

**Decision: PASS** (contributor self-check; User visual acceptance remains pending; Sara submission had not yet been updated at self-check time).

**Reviewed head:** `7afda3394dfd1ccc6e85837eacda75a04ff3b9f8`

**Generator correctness:** PASS. **Runtime provenance:** PASS, NEW/REPLACEMENT.

**Declared scaling target:** 100,000 accepted cases. **Declared-target scale readiness:** PASS.

**Audited media:** exactly two submitted seeds, 42 and 98; eight formal native streams. Static 100,000-profile validation is not a claim of 100,000 rendered cases. Controlled probes are explicitly smoke-resolution evidence.

**Production readiness:** PRODUCTION READY under the analytical-trajectory, real-3D rendering contract reviewed here; no simulator-native dynamics claim.

## Blocking findings

None remaining in the six-gate generator and delivered-media contract. No fresh rerender-and-compare execution is claimed; standalone reproduction/compare entry points and deterministic trajectory tests were inspected/tested. The inherited upstream README/CITATION license wording differs from the upstream LICENSE; this review grants no additional rights and leaves upstream licensing terms intact.

## Closed human-feedback findings

Beam: the 1.6:1 side-face thickness contrast was too subtle; now 3.5:1 with a closer view. Screw: fast rotation over roughly 1.3 seconds obscured the normal coupling; now slower rotation over more than two seconds, wider lead, contrasting gold helix and a real off-axis crank. Rod: the 0.36 m silver crosshead travel was hard to read; now 0.85 m extension, gold moving pull feet and pistons, and an actual hollow-cylinder port. Each applicable fix is checked against final decoded media rather than only parameters.

## Six-gate result

| Check | Result | Evidence |
|---|---|---|
| Output contract | PASS | Eight formal 2048² H264 RGB streams: 24 fps, 120 frames, five seconds; independently ffprobed and fully decoded. |
| Violating-object-only mask | PASS | Only guided nut, attached carriage and its thread ribs/connection; shaft, guide rails, pawl and bearings excluded. Every formal pixel is 0 or 255, equal channels; active window exactly matches metadata. |
| Real scaling | PASS | 100,000 CPU profiles; primary axes separately rendered at 512²; two native 2048² cases across different length/response/onset/appearance/view buckets. |
| Official unpatched environment | PASS | Clean exact source head, official Python 3.11.17 + bpy 4.5.3, real Tesla T4 OpenGL renderer, pinned packages and actual encoder witness. |
| Decoded matched control | PASS | All 120 frames of True/CF/mask/overlay independently decoded; exact prefix equality and red-only active-mask replacement. |
| Semantic consistency | PASS | The visible handwheel and screw initially turn and drive the guided half-section cutaway nut through a clearly visible ordinary advance lasting over two seconds, with gold screw threads and an off-axis crank handle. The visible pawl locks the shaft. True nut stops; CF nut continues axially while both screw and nut cease rotation. Bearings, guide holes and continuous male helix remain visible. Relative thread passage is the declared coupling violation. README, title, registered operator, predicates and independent prompts inspected together. |

## Production-quality behavioral baseline

| Check | Result | Evidence |
|---|---|---|
| True completes the correct prompt outcome | PASS | The visible handwheel and screw initially turn and drive the guided half-section cutaway nut through a clearly visible ordinary advance lasting over two seconds, with gold screw threads and an off-axis crank handle. The visible pawl locks the shaft. True nut stops; CF nut continues axially while both screw and nut cease rotation. Bearings, guide holes and continuous male helix remain visible. Relative thread passage is the declared coupling violation. |
| Counterfactual has exactly one physical error | PASS | Independent pitch × angle / 2π relation before lock; zero shaft/nut rotation after lock with CF-only axial drift. |
| Both independent prompts match their respective videos | PASS | Both seeds reviewed against source, full decoded sequences, and actual browser playback; prompts reproduced below. |
| Matched setup and branch identity | PASS | Exact decoded prefix, shared camera/color/support/latch conditions, correctly labeled paths. |
| No undeclared anomaly or unrelated geometry failure | PASS | Continuous 3D meshes, contacts and native selected frames reviewed; stated thread passage is part of the screw violation. |
| Completion, observation tail and final visibility | PASS | All streams play all 120 frames; visible final outcomes; no target crops, minimum borders in independent report. |
| Phenomenon-specific plausibility | PASS | Independent pitch × angle / 2π relation before lock; zero shaft/nut rotation after lock with CF-only axial drift. |

## Timebase and playback integrity

| Check | Result | Evidence |
|---|---|---|
| Source seconds per video second | PASS | Trajectory t[n]=n/24, 24fps video: 1 source second per video second; last sample 119/24, container duration 5s. |
| Outer steps versus solver substeps | NOT APPLICABLE | Analytical sampled states; no undocumented solver substeps or time scaling. |
| Intentional and pair-matched speed | PASS | Shared timebase and camera; full sequences inspected, no slow/fast-motion label shortcut. |
| Timebase remediation | NOT APPLICABLE | No time mapping changed during remediation. |

## Optional simulator-profile result

Not applicable: Blender Workbench renders analytical trajectories and is not presented as their physics solver.

## Semantic matrix

Title, generator README, registered operator, scoring predicate and both rendered branches describe the same phenomenon: Independent pitch × angle / 2π relation before lock; zero shaft/nut rotation after lock with CF-only axial drift.

Seed 42:

True: A rotating lead screw drives a threaded cutaway nut along a visible anti-rotation guide. A latch then locks the screw against rotation; the bearings hold it against axial motion. The nut advances while the screw turns, then stops and remains engaged on the locked screw.

Counterfactual: A rotating lead screw drives a threaded cutaway nut along a visible anti-rotation guide. A latch then locks the screw against rotation; the bearings hold it against axial motion. The nut advances while the screw turns, but after the screw locks the still-engaged nut continues moving axially even though neither the screw nor the guided nut rotates.

Operator: `locked_helical_coupling_axial_drift`; onset 56; visible change 56; physical evidence 59.

Seed 98:

True: A rotating lead screw drives a threaded cutaway nut along a visible anti-rotation guide. A latch then locks the screw against rotation; the bearings hold it against axial motion. The nut advances while the screw turns, then stops and remains engaged on the locked screw.

Counterfactual: A rotating lead screw drives a threaded cutaway nut along a visible anti-rotation guide. A latch then locks the screw against rotation; the bearings hold it against axial motion. The nut advances while the screw turns, but after the screw locks the still-engaged nut continues moving axially even though neither the screw nor the guided nut rotates.

Operator: `locked_helical_coupling_axial_drift`; onset 60; visible change 60; physical evidence 62.

## Verified passes

Independent measurements for both accepted cases:

```json
[
  {
    "case_id": "locked_lead_screw_nut_axial_drift_00000042",
    "first_changed_frame": 56,
    "mask_end_frame": 120,
    "minimum_target_border_px": 641,
    "physical_witnesses": {
      "cf_drift": 0.5135,
      "post_lock_shaft_rotation": 0,
      "nut_rotation": 0,
      "evidence_frame": 59
    }
  },
  {
    "case_id": "locked_lead_screw_nut_axial_drift_00000098",
    "first_changed_frame": 60,
    "mask_end_frame": 120,
    "minimum_target_border_px": 414,
    "physical_witnesses": {
      "cf_drift": 0.71825,
      "post_lock_shaft_rotation": 0,
      "nut_rotation": 0,
      "evidence_frame": 62
    }
  }
]
```

## Successful-render runtime provenance

| Check | Result | Evidence |
|---|---|---|
| Exactly one successful witness per submitted case | PASS | runtime-witness-index.json plus official fail-closed runtime audit; two accepted cases. |
| Commit, source state, command and seeds | PASS | runtime-witness.json binds this exact clean head and seeds42,98. |
| Actual components and delivered hashes | PASS | Python/bpy/packages/OS/GPU/OpenGL/driver and actual encoder binary hash/version retained; SHA-256 inventory audited. |
| Nested runtime | NOT APPLICABLE | bpy executes in the same recorded Python process; no separate Blender embedded interpreter. |
| Reproduction recipe | PASS | Standalone examples/reproduce.py and compare.py; historical successful runtime evidence is separately retained. |

## Client-facing artifact consistency

| Check | Result | Evidence |
|---|---|---|
| Browser playback and seeking | PASS | All eight HTML streams actually played to ended=true, duration/currentTime=5, error=null; all eight sought to the evidence time without error. The actual seeking receipt and visual inspection are retained. |
| Black/white masks and red overlays | PASS | Actual browser frames inspected; no green/magenta/channel swaps or blank media. |
| Formal overlay consistency | PASS | Every decoded formal off-mask pixel equals CF; every active pixel is [255,0,0]; no shadows. |
| Review derivatives | PASS | HTML clearly labels 1024² lossy yuv420p copies separately from formal lossless 2048² RGB files. |

## Scale-readiness result

| Check | Result | Evidence |
|---|---|---|
| CGC-v1 deterministic coverage | PASS | 100,000 accepted static signatures/profile IDs, 100M profile space, all axis buckets covered; zero reported errors. |
| Independent primary axes reach rendered output | PASS | Clean exact-head axis-probes.json: length, response, onset low/high rendered independently; recorded PNG hashes and per-image MAD/changed pixels. |
| Formal material diversity | PASS | Seeds42/98 differ across all five relevant buckets; two native decoded clips visibly differ in dimensions, response, onset, palette and view. |
| Pair-shared nuisance variation and exact prompts | PASS | Scene/camera/color shared within each pair; incidental profile IDs are absent from prompts. |
| Sharding/quota and manifests | PASS | Canonical eight-shard disjointness audit; source/output SHA-256 manifests; accepted-case quota checked. |
| Safe resume | PASS | Actual compatible resume fully decoded existing cases; incompatible quota rejected. Every generator reruns this check from its new exact head; the per-generator log is retained. |
| Fail-closed runtime and media audits | PASS | Official runtime witness audit and independent full final-MP4 decoding; no monkey patches. |

## Commands and artifacts checked

`python -m compileall`, `python -m pytest`, official `examples/generate.py`, canonical `examples/audit_scaling.py`, controlled `examples/probe_axes.py`, official run/audit/index provenance scripts, independent_review.py and anonymous full-file HTTP hash/Range verification. Evidence is linked from review.html and included in packet-manifest.json.

## Re-review requirements

Any source-head change requires fresh applicable exact-head evidence and a new versioned public packet. Sara's review is independent of this contributor self-check.
