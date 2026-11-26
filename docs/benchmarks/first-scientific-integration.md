# First scientific integration: preliminary benchmark
Date: 2026-11-26. Model: DESY API identifier coding; underlying model version not independently verified. Target: local cylindrical waveguide solver, Library archive dated 2026-10-22, version 7; no Git revision or remote exists. Target overlays Stages 1–4, synthetic configurations, exact request records and application tests are kept outside this repository.

Initial four valid synthetic requests (original, missing optional controls, changed mode/anisotropy, open exterior) took 11.5, 17.7, 17.1 and 45.9 seconds. First three passed manual core scientific review; the fourth conflated a mode index with a physical effective index and used ambiguous index terminology. A missing required material field was rejected locally, without a request.

Alternating prompt comparison on one identical open-exterior fixture:
| Prompt | Repeat | Seconds | Core scientific assessment |
|---|---:|---:|---|
| 1.0 | 1 | 18.494 | Fail: index definitions and effective index |
| 1.1 | 1 | 17.330 | Pass |
| 1.0 | 2 | 23.144 | Pass |
| 1.1 | 2 | 17.220 | Pass |
| 1.0 | 3 | 20.865 | Fail: reversed index definitions |
| 1.1 | 3 | 25.717 | Pass |

All API requests succeeded. All six got geometry, material settings and open boundary interpretation correct. One revised response calculated a correct but unrequested ratio. Original mean 20.834 s, revised mean 20.089 s; no meaningful speed inference. Revised wording renamed the ambiguous field and defined both index conventions, so the effects are not isolated. Manual assessment not blinded, small sample, no formal statistical claim. Keep exact prompts and raw logs in target workspace; repeat the paired fixture with independently recorded responses for reproduction. No application data or code reproduced here.

Live Stage 4 GUI response: 24.5 s, core scientific claims correct, user found exhaustive reporting overwhelming. Offline Stage 4 reports 39 AI unit tests, 5 GUI integration tests, 5 loader-parity checks and 23 selected existing regression tests passed; standalone GUI checks also passed. Live Windows GUI success reported by user. No full regression claim. Next: evaluate question-driven UI with short targeted questions, follow-ups, current versus saved source distinction and explicit consent. See [architecture proposal](../architecture/unified-ai-assistant.md).
