# G1 independent specification review — PASS

**Identity:** Step `000-01-phase-0-baseline`, G1 attempt 03. Reviewer `/root/g1_baseline_a03_retry`, fresh-context non-author. Reviewed 2026-09-30, ending 16:28:49 America/Bogota. Intended report path: `docs/piraxe/reviews/000-01-phase-0-baseline-G1-a03.md`. This was a read-only review in the shared checkout; no separate filesystem copy was used. I did not edit, stage, commit, or push.

**Candidate:** `C:\Users\rosog_mfeqzsa\.codex\.chatgpt-projects\g-p-6ab83e1f78d08191a2796fd4f913e669\piraxe-openmontage\OpenMontage`; branch `docs/piraxe-project-context`; HEAD and local `main`/base `08e2151fa02de28a5d6a312b3d575692bf147ad7`; index empty. The review manifest contains three modified tracked root files and 30 untracked files, excluding the prospective archive: 33 regular files, no symlink, deletion, rename, tracked mode change, application-code change, or generated asset. The separate untracked archive was inspected but is ineffective pending a verified commit.

**Verdict: `PASS`.** The specification remains grounded in the user’s request for a scoped local commit of the current Phase 0 files. Its requirements, owned paths, branch/base, recovery procedure, and G1/G2/G3/post-commit checks are implementable. The four substantive documentation changes since G2 attempt 02 are exactly one removed terminal LF per file. The spec and current authority, plan, and status contract hashes reproduce the prior current G1 contract. This verdict applies only to the exact contract and candidate snapshot below.

| G1 item | Independently inspected evidence | Result |
|---|---|---|
| User request and scope | User’s “commit the current files” request; full spec revision 1; Plan 000; root diff; 33-file Git inventory and empty index. The outcome is a local documentation commit, with no push, merge, provider implementation, or first feature included. | PASS |
| Branch, base, ownership, dependencies | Git branch/HEAD/main/remotes; `CURRENT_STEP.md`, `STATUS.md`, Plan 000 and `BRANCHING.md`. Three tracked root edits and untracked `docs/piraxe/` plus three local skill trees remain within the declared Phase 0 surfaces. No prior build-step dependency. | PASS |
| Architecture and verified facts | `PROJECT_CONTEXT.md`, PIRAXE vision/architecture/roadmap/decisions, root diff, tracked baseline tool/selector/schema/checkpoint/cost paths, and `pipeline_defs/cinematic.yaml`. The latter actually requires at least three cinematic directions and three concept options. Provider APIs remain unverified and outside this step. | PASS |
| Implementable contracts and failure/recovery | R-01–R-06, allowed paths and T-01–T-05 in the spec; `BUILD_WORKFLOW.md`, `REVIEW_BRIEF.md`, three local skills, spec template, closeout procedure and failed-preflight journal. The journal’s saved preimages verify; the active slot and ledger are not falsely completed. | PASS |
| Requirement-to-check traceability | R-01/R-02→AC-01; R-03→AC-02; R-04→AC-03; R-05→AC-04; R-06→AC-05. AC-01–AC-03 are due G2, staged archive/index AC-04 is due G3, and actual parent/tree/trailer/clean-tree AC-05 is due post-commit. | PASS |
| Feasible validation and unknowns | Offline Git, document inspection, local link checks and installed skill validator are specified. No paid/live provider call is needed. Paipu BK/Nano Banana API details, terminology review, and branch integration are explicitly deferred beyond this documentation commit. | PASS |
| Snapshot currency | Spec, section hashes, baseline blobs, complete candidate manifest, branch/HEAD/main and empty index were computed independently; manifest and Git identity matched at the final recheck. | PASS |

**Manifest rule:** Take paths from `git diff --name-only` plus `git ls-files --others --exclude-standard`; exclude only the prospective `docs/piraxe/completed/000-01-phase-0-baseline.md` from this G1 candidate manifest. Sort case-insensitively as PowerShell `Sort-Object -Unique` does. For each path record `path=UPPERCASE_SHA256_OF_FILE_BYTES`, join with LF and a final LF, and SHA-256 those UTF-8 bytes. The 33-file digest, reproduced by Python and PowerShell and unchanged at the final recheck, is `021459603A6B0E8150F9F4237E8507EA0C6F63B14FCDB2258EE20A5CAB552B07`.

```text
.agents/skills/commit/agents/openai.yaml=BA503CC1A8A3DEA8045FCB4FABDDD4FCB0408A17A36F02AB6DF8C9E325D158D0
.agents/skills/commit/references/closeout.md=AA96600D3EB2277755E10B1CE376E1054E777D7D21DC4EBC8321E2C197F6825F
.agents/skills/commit/SKILL.md=C41CD6D93D0F94F0E789D6ADAB764D6E89636796912DD29C00095679521FEED5
.agents/skills/inplement/agents/openai.yaml=52E0C2C159C24726A14FF45920C09386CFDFA1178B83CCA7F111EDC1025D2277
.agents/skills/inplement/SKILL.md=5E9457809FA13085A9936916E9AF48E662C63932790719CACE9598754FDDD589
.agents/skills/spec/agents/openai.yaml=3900FFE653625A520C48D0105DB22554A32C284EE1E6D6432EF67124E93ED4F7
.agents/skills/spec/assets/step-spec-template.md=08E100BD6A2E4B7059F760D590388F0D695A7B5975F5A880A423D6926A8BC307
.agents/skills/spec/SKILL.md=B03A2C38F3B7C84EF7A15F921C7FC5B12ADD8544FA2A15DB5F7DB0534CB0A832
AGENT_GUIDE.md=7C0470CC4D7FBEF7433C96DDFAE94DCC4E847828F6901D8744AFA0A30B769F23
AGENTS.md=55E67D0927D4AB8218812CD836136B508692A6882606558C876DC825985134D3
docs/piraxe/ARCHITECTURE.md=C06C368E65FBFAC97CF484830F825CFC8B5506862E6283CC63B37247FD315F0A
docs/piraxe/BRANCHING.md=1416A4AEA3235BAB08ECB6B840F1DEC1DB222EB0179D89617F2ADE3C07BC3C8B
docs/piraxe/BUILD_WORKFLOW.md=B8AB7773B8B4FEBE66A595E84D52557C2A343081AFE534FAEFA45B36A5D87BC6
docs/piraxe/CURRENT_STEP.md=5E001ED7ECE971AFBF1FC9179FB4466C9E40609A05EE837F5CABE85A793BED31
docs/piraxe/DECISIONS.md=51BA40BF9C546C35D97D19A9C5D8732B3F3A1988EADB3A0451234A05952604BC
docs/piraxe/plans/000-project-memory.md=17C6FC9F1D2FB483E5C9E66899A59136A37A7E9301F45C07CF4174C358F486A1
docs/piraxe/plans/001-architecture-audit.md=559908F511E38FA55FAFD3A4E41CE8269AF4D9728B35BE47494F5F323E3164EB
docs/piraxe/plans/README.md=CD1FC12059E6062286F2C1D35F4663FB26F406D30588139CFC1875798FBD1E99
docs/piraxe/plans/TEMPLATE.md=78ADE0E2F3F351448F500891367FC1E06BB221F69E3113A9D056A4262392C472
docs/piraxe/README.md=DBC72AB29DFAC6FB8762BF473A587E4DB7371C10E4FA0B0B56F379B14889E0FC
docs/piraxe/REVIEW_BRIEF.md=1B09EA93FCF6D19922491E32DD6213319B4DA30512A0F2F1F7A9B2B4D704B367
docs/piraxe/reviews/000-01-phase-0-baseline-G1-a01.md=91CAA7D6BF06C40A3AD134DA2C3CEAA8A8E3A939A8B0E4C8BDF94592EBA39014
docs/piraxe/reviews/000-01-phase-0-baseline-G1-a02.md=63173E37770D89C9BDEA398F9F1015EE3A4AE3D4A43F10335746A5A88B432283
docs/piraxe/reviews/000-01-phase-0-baseline-G2-a01.md=4C6A2F0943AE4555E79B0DA85AA16A194DE97017D32C667D62668DE4510AEB07
docs/piraxe/reviews/000-01-phase-0-baseline-G2-a02.md=448670FE6A9712A4CB4F83211498240B88870BA7EFB61CB0D967A05F5228B5CE
docs/piraxe/reviews/2026-09-29-skill-instruction-review.md=0609B748BD637F577B768ABD97CD79C3910988DFEE206157933CD9295F25D910
docs/piraxe/reviews/2026-09-29-skill-validation.md=EE8DF7901D0C40370FF485F8305731CE8E129D0E4845BE8B3138987AA2B16A3D
docs/piraxe/ROADMAP.md=E0E3DEE30F69829EA52BD5B14A7CFAD10DBEDE2CCF1C02EA76D3975848C8AD51
docs/piraxe/specs/000-01-phase-0-baseline.md=109B6AA7328CAFA4198B1D9C7842BCE93E8662F93A506D142236E514C2FDCE08
docs/piraxe/STATUS.md=6F713E02EBC3CEF92C00DF225071E6340A5700A3259B6AA10C27498FB133475A
docs/piraxe/STEPS.md=8560E3F9B0D20E61800EDF1EF7584F02E76CD967FC7FCE08C023ACFD9DE2AF76
docs/piraxe/VISION.md=BD0B1FB6C836D96911E10F0AD54CC2B25A8C02A93080BB34663D27D0316B0186
PROJECT_CONTEXT.md=2B2ECD22BF75694F3213D12FD330445845FF65257A446A6EF62C6906D00DDDDB
```

**Current contract hashes and extraction rules:**

- Full spec revision 1 SHA-256: `109B6AA7328CAFA4198B1D9C7842BCE93E8662F93A506D142236E514C2FDCE08`.
- `CURRENT_STEP.md` identity/authority/ownership SHA-256: `58D491B855F87FCD919BBA59A33EFA672EC58D907C66D543D9CD431A36635AD8`. Decode UTF-8 without newline normalization; take from first character up to but excluding the first exact `\n## Tasks`; remove the entire `- State:` line including its terminating LF with `(?m)^- State:.*(?:\r?\n)`; hash the resulting UTF-8 bytes.
- Plan 000 contract SHA-256: `324A00C7CE7B0850F18AA5B8300DE6CC1FC76F9AA9C6B4D11DC5962EDEB5D04F`. Take from first `## Outcome` up to but excluding the next `\n## Validation`; replace literal `- [x]` with `- [ ]`; hash UTF-8 bytes.
- `STATUS.md` branch/base/plan identity SHA-256: `CD528E7247B9EB6429C5DB6F4032D77CF528DBB05146A99E4E1EFD24E6C32B66`. Retain LF-split lines matching `^- (Current branch|Base branch|Active plan):`, join with LF without final LF, and hash UTF-8 bytes.

These four hashes reproduce G1-a02’s stated current contract. Its fixed inspected base is HEAD `08e2151…`. The Git index blobs and modes for the root baseline remain `AGENTS.md` `7649447bc320e098a06e95fe5dbc3e9a7539888b`, `AGENT_GUIDE.md` `b27b09a026e44ed90c60f6410a5e3934b51e228d`, and `PROJECT_CONTEXT.md` `5f0db30167a41189c1bc65bde96ba84b234535b5`, each `100644`.

**Change comparison against G2-a02:** Parsing its 32-line manifest and rehashing every recorded path showed only seven changed hashes: the four EOF files plus `CURRENT_STEP.md`, Plan 000, and `STATUS.md`. The latter three contain the recorded failed-preflight/progress handoff; their retained contract section hashes above did not change. The only new paths are G2-a02’s own report and the prospective archive. No prior path is missing. For each EOF file, current bytes end in exactly one LF, and SHA-256 of `current bytes + b"\n"` exactly equals its old G2-a02 hash:

| File | Current SHA-256 | G2-a02 SHA-256 restored by one LF |
|---|---|---|
| `docs/piraxe/ARCHITECTURE.md` | `C06C368E65FBFAC97CF484830F825CFC8B5506862E6283CC63B37247FD315F0A` | `D589AEB3E5C9CDD62AD0696E58B6FEA186AEF0C6E33EDC5AE3CCAAF7528D5D03` |
| `docs/piraxe/VISION.md` | `BD0B1FB6C836D96911E10F0AD54CC2B25A8C02A93080BB34663D27D0316B0186` | `D1FD2D250F4527280270D1B15037881EEC7E523D22CFDD42CBF48038CDD42494` |
| `docs/piraxe/plans/001-architecture-audit.md` | `559908F511E38FA55FAFD3A4E41CE8269AF4D9728B35BE47494F5F323E3164EB` | `BD89DC4D5C07C9E003B31EA55FDFEA39247EF288CBBB5DB36599E4ED704E8C28` |
| `docs/piraxe/plans/TEMPLATE.md` | `78ADE0E2F3F351448F500891367FC1E06BB221F69E3113A9D056A4262392C472` | `8BA6AFCD9A23B9D7DEF5B07C4794F3DF200CE9722B13233D2949A9CC0FEE69BB` |

**Recovery-state inspection:** `.git/piraxe-closeout/000-01-phase-0-baseline/journal.json` is attempt 01 in `failed_preflight` state. It records `index_restored: true`, `metadata_restored: true`, no push authority, and no original staged entries. All four saved preimage files exist and match their recorded SHA-256 hashes. The journal’s candidate archive hash matches the retained untracked archive. The current step is `spec_review`, the ledger entry is unchecked, the archive calls itself prospective and says completion requires a verified trailer-bearing commit, the index is empty, and `git log --all --grep='PIRAXE-Step: 000-01-phase-0-baseline'` returned no closing commit. Thus no completed step is being inferred from the failed transaction.

**Independent commands and results:** All ran at repository root in the offline Windows PowerShell checkout. `Get-Content -Raw -Encoding UTF8` of the mandatory guide, memory reading-order files, full spec/plan, prior G1-a02/G2-a02 reports, three local skills, template, closeout procedure and archive exited 0. `git branch --show-current`, `git rev-parse HEAD`, `git rev-parse main`, `git remote -v`, `git status --porcelain=v1 -uall`, `git diff --name-status`, `git diff --cached --name-status`, `git diff --summary`, `git diff --check`, `git ls-files -s -- AGENTS.md AGENT_GUIDE.md PROJECT_CONTEXT.md`, relevant baseline `git ls-files`, and application-path `git status --short` exited 0 with the observations above. `rg -n -i "three|concept|direction|research" pipeline_defs/cinematic.yaml skills/pipelines/cinematic/idea-director.md` exited 0 and located the three-direction and three-option constraints. `git config --get core.hooksPath` exited 1, indicating no custom hooks path. `git log --all --grep` exited 0 with no matching commit.

Read-only Python scripts independently computed the 33-file manifest, section hashes, prior-manifest comparison, exact EOF-byte reversibility, file types and journal/preimage assertions; corrected runs exited 0. One exploratory journal parse exited 1 because the JSON file has a UTF-8 BOM; parsing with `utf-8-sig` exited 0 and verified the assertions. A separate PowerShell SHA-256 manifest computation exited 0 with the same digest. Final PowerShell recheck at 16:28:49 -05:00 returned the same 33-file digest, branch, HEAD/main and empty index. No G2 validator, staging, G3 review, application test, live service, commit, or push was run during G1.

**Findings:** No required G1 finding. The retained prospective archive still names G1/G2 attempt 02 and G3 attempt 01. Before any G3 closeout, it must be rebuilt from the current reports and failed-preflight history; this is a later closeout-record obligation, not a defect in the reviewed specification.

**Declared narrow exclusions and limits:** This generated G1-a03 report; later G2/G3 report receipts and check results; lifecycle state, checklist marks and execution evidence in `CURRENT_STEP.md`; validation/progress/handoff entries in Plan 000; progress/delivery text in `STATUS.md`; and the prospective archive and Git-local closeout record. The mixed-file contract sections remain hashed above. No spec, authority/ownership prefix, Plan outcome/scope/dependencies/acceptance, branch/base/plan identity, instruction, architectural contract, or candidate documentation content is exempt. The excluded archive/journal were inspected for truthfulness and must be fully reviewed at G3. The historical entry instant with exactly 25 untracked files cannot be reconstructed from Git. G2-due content checks, G3’s actual staged tree/archive and post-commit verification remain pending at their specified gates.

**Gate exit and invalidation:** G1 passes for this branch, base, spec revision, contract hashes and inspected baseline. Recompute the hashes before accepting the verdict and before G2. A changed spec, authority/ownership prefix, Plan contract, branch/base/plan identity, instruction/dependency contract, unexpected candidate path/mode, or further substantive documentation change invalidates the affected review. Intended progress and report-receipt updates require later-gate inspection; they do not alone alter the reviewed G1 contract.
