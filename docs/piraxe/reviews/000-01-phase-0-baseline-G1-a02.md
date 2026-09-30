# G1 independent specification review — PASS

**Identity:** Step `000-01-phase-0-baseline`, G1 attempt 02. Reviewer `/root/g1_baseline_a02`, fresh-context non-author. Reviewed 2026-09-29 21:48 America/Bogota. Intended report path: `docs/piraxe/reviews/000-01-phase-0-baseline-G1-a02.md`. Review was read-only in the shared checkout; no filesystem isolation was used.

**Candidate:** `C:\Users\rosog_mfeqzsa\.codex\.chatgpt-projects\g-p-6ab83e1f78d08191a2796fd4f913e669\piraxe-openmontage\OpenMontage`, branch `docs/piraxe-project-context`, HEAD and local `main`/base `08e2151fa02de28a5d6a312b3d575692bf147ad7`. Index empty. Inventory: three modified tracked root files and 28 untracked files, all within the Phase 0 surfaces. All 31 paths are regular files. No application-code changes, deletion, rename, tracked mode change, or generated asset appeared. The complete manifest and Git identity matched before and after inspection.

**Verdict: `PASS`.** This is a new review of the *present* spec and authority/ownership contract. It does not explain or retroactively validate the unreproducible prefix hash in G1 attempt 01. The current contract has a new, reproducibly defined hash below, resolving the G2 attempt 01 currency blocker for this snapshot.

| G1 item | Inspected evidence | Result |
|---|---|---|
| User-grounded outcome and ownership | User’s local-commit request; spec identity/scope; Plan 000; complete Git inventory and empty index | PASS |
| Architecture and dependencies | Root diff; `PROJECT_CONTEXT.md`; PIRAXE vision, architecture, roadmap, decisions, branching; unchanged tracked tool, selector, schema and pipeline paths | PASS |
| Exact branch, base, scope | Spec, Plan 000, `CURRENT_STEP.md`, `STATUS.md`, Git branch/HEAD/main/remotes; no prior step dependency | PASS |
| Implementable contracts and recovery | R-01–R-06, allowed paths, tasks, `BUILD_WORKFLOW.md`, three local skills and closeout procedure | PASS |
| Requirement-to-check mapping | R-01/R-02→AC-01; R-03→AC-02; R-04→AC-03; R-05→AC-04; R-06→AC-05 | PASS |
| Gate timing and feasible checks | AC-01–AC-03 due G2; staged candidate/archive AC-04 due G3; actual commit AC-05 due post-commit. Offline inspection, installed validator, Git and link checks are feasible. | PASS |
| Essential unknowns | Paipu BK and Nano Banana API questions, terminology review and branch integration are expressly outside this documentation commit. No provider API fact is assumed. | PASS |
| Snapshot identity | Spec hash, section hashes, 31-file manifest, base blobs and Git state checked twice | PASS |

**Manifest rule:** For the paths returned by `git diff --name-only` plus `git ls-files --others --exclude-standard`, sort paths with PowerShell `Sort-Object -Unique`. Record each as `path=UPPERCASE_SHA256_OF_FILE_BYTES`; join records with LF and a final LF; SHA-256 the resulting UTF-8 bytes. The 31-file manifest digest was `BA788C99DBD7E6D3BA166BDED29E938CC7D8F7A3709D157382189837EE6A09FD` at both checks.

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
docs/piraxe/ARCHITECTURE.md=D589AEB3E5C9CDD62AD0696E58B6FEA186AEF0C6E33EDC5AE3CCAAF7528D5D03
docs/piraxe/BRANCHING.md=1416A4AEA3235BAB08ECB6B840F1DEC1DB222EB0179D89617F2ADE3C07BC3C8B
docs/piraxe/BUILD_WORKFLOW.md=B8AB7773B8B4FEBE66A595E84D52557C2A343081AFE534FAEFA45B36A5D87BC6
docs/piraxe/CURRENT_STEP.md=562DD369F9292AF83AA3142C0D3F2A00C1DD3C16F93A81E5B4C95254BD5DD9EF
docs/piraxe/DECISIONS.md=51BA40BF9C546C35D97D19A9C5D8732B3F3A1988EADB3A0451234A05952604BC
docs/piraxe/plans/000-project-memory.md=73A1A0D4F986DE8BB9152529FF97B7EEB64F587F863AA7D38B482BD42F0CB8C9
docs/piraxe/plans/001-architecture-audit.md=BD89DC4D5C07C9E003B31EA55FDFEA39247EF288CBBB5DB36599E4ED704E8C28
docs/piraxe/plans/README.md=CD1FC12059E6062286F2C1D35F4663FB26F406D30588139CFC1875798FBD1E99
docs/piraxe/plans/TEMPLATE.md=8BA6AFCD9A23B9D7DEF5B07C4794F3DF200CE9722B13233D2949A9CC0FEE69BB
docs/piraxe/README.md=DBC72AB29DFAC6FB8762BF473A587E4DB7371C10E4FA0B0B56F379B14889E0FC
docs/piraxe/REVIEW_BRIEF.md=1B09EA93FCF6D19922491E32DD6213319B4DA30512A0F2F1F7A9B2B4D704B367
docs/piraxe/reviews/000-01-phase-0-baseline-G1-a01.md=91CAA7D6BF06C40A3AD134DA2C3CEAA8A8E3A939A8B0E4C8BDF94592EBA39014
docs/piraxe/reviews/000-01-phase-0-baseline-G2-a01.md=4C6A2F0943AE4555E79B0DA85AA16A194DE97017D32C667D62668DE4510AEB07
docs/piraxe/reviews/2026-09-29-skill-instruction-review.md=0609B748BD637F577B768ABD97CD79C3910988DFEE206157933CD9295F25D910
docs/piraxe/reviews/2026-09-29-skill-validation.md=EE8DF7901D0C40370FF485F8305731CE8E129D0E4845BE8B3138987AA2B16A3D
docs/piraxe/ROADMAP.md=E0E3DEE30F69829EA52BD5B14A7CFAD10DBEDE2CCF1C02EA76D3975848C8AD51
docs/piraxe/specs/000-01-phase-0-baseline.md=109B6AA7328CAFA4198B1D9C7842BCE93E8662F93A506D142236E514C2FDCE08
docs/piraxe/STATUS.md=A3A4818630F08CCBCACE2017904FE796D4D1BC4A5BDC125F5DD76570F88DE302
docs/piraxe/STEPS.md=8560E3F9B0D20E61800EDF1EF7584F02E76CD967FC7FCE08C023ACFD9DE2AF76
docs/piraxe/VISION.md=D1FD2D250F4527280270D1B15037881EEC7E523D22CFDD42CBF48038CDD42494
PROJECT_CONTEXT.md=2B2ECD22BF75694F3213D12FD330445845FF65257A446A6EF62C6906D00DDDDB
```

**Contract hashes and extraction rules:**

- Full spec file SHA-256: `109B6AA7328CAFA4198B1D9C7842BCE93E8662F93A506D142236E514C2FDCE08`.
- `CURRENT_STEP.md` identity/authority/ownership SHA-256: `58D491B855F87FCD919BBA59A33EFA672EC58D907C66D543D9CD431A36635AD8`. Decode the file as UTF-8 without newline normalization. Take the substring from its first character up to, but excluding, the first exact `\n## Tasks`. Remove the entire line beginning `- State:` including its terminating LF with regex `(?m)^- State:.*(?:\r?\n)`. SHA-256 the UTF-8 bytes of the resulting string. This retains the step ID, spec/plan links, branch/base/HEAD, authority and ownership. It was reproduced at both checks.
- Plan 000 contract SHA-256: `324A00C7CE7B0850F18AA5B8300DE6CC1FC76F9AA9C6B4D11DC5962EDEB5D04F`. Decode as UTF-8; take from the first `## Outcome` through immediately before the first `\n## Validation` following it; replace literal `- [x]` with `- [ ]`; hash the UTF-8 result.
- `STATUS.md` branch/base/plan SHA-256: `CD528E7247B9EB6429C5DB6F4032D77CF528DBB05146A99E4E1EFD24E6C32B66`. Decode as UTF-8; split on LF; retain lines matching `^- (Current branch|Base branch|Active plan):`; join with LF and no final LF; hash the UTF-8 result.

The fixed inspected base is HEAD `08e2151…`; Git index blobs/modes for the root files are `AGENTS.md` `7649447bc320e098a06e95fe5dbc3e9a7539888b`, `AGENT_GUIDE.md` `b27b09a026e44ed90c60f6410a5e3934b51e228d`, and `PROJECT_CONTEXT.md` `5f0db30167a41189c1bc65bde96ba84b234535b5`, each `100644`. Relevant tool, selector, checkpoint, cost, cinematic manifest and artifact schema paths are unchanged tracked baseline files.

**Declared narrow exclusions:** This generated G1-a02 report; later G2/G3 report receipts and check results; lifecycle state, checklist marks and execution evidence in `CURRENT_STEP.md`; validation/progress/handoff entries in Plan 000; and progress/delivery text in `STATUS.md`. These exclusions do **not** cover the spec, authority/ownership prefix, Plan 000 outcome/scope/dependencies/acceptance, branch/base/plan identity, instructions, architectural contracts or candidate code/content. Later bookkeeping must be inspected at its due gate.

**Independent commands:** All ran at repository root in the offline Windows PowerShell checkout. `Get-Content` of the mandatory guide, memory reading-order documents, full spec, skills, template, closeout procedure and prior reports exited 0. `git branch --show-current`, `git rev-parse HEAD`, `git rev-parse main`, `git remote -v`, `git status --porcelain=v1 -uall`, `git diff --name-status`, `git diff --cached --name-status`, `git diff --summary`, `git diff --check`, `git ls-files -s -- AGENTS.md AGENT_GUIDE.md PROJECT_CONTEXT.md`, `git ls-files -- <relevant baseline paths>`, and `git status --short -- tools pipeline_defs schemas tests lib backlot` exited 0 with the observations above. `git config --get core.hooksPath` exited 1 with no custom hook path. `git rev-parse --git-path piraxe-closeout` exited 0; that journal directory was absent. The PowerShell SHA-256 manifest and section-hash scripts exited 0 twice with identical digest, spec, contract, branch, HEAD and empty-index assertions. No G2 validator, application test, live service, staging, commit or push ran during this G1 review.

**Findings:** No required G1 finding. For G2/G3 accuracy review, Plan 000’s Handoff says `Blocker: None` although its own validation row and `STATUS.md` record the G2-a01 blocker. Correct the live progress wording before closeout; this is an execution-record issue, not a defect in the reviewed specification.

**Unverified at G1:** The historical instant with exactly 25 untracked entry files cannot be reconstructed from Git; the present 28 untracked files are accounted for. AC-01–AC-03 independent implementation checks remain due at G2. The archive/staged tree and actual commit do not yet exist, so AC-04 and AC-05 remain due at G3 and post-commit. No provider behavior or remote delivery was tested or claimed.

**Gate exit and invalidation:** G1 passes for this exact branch, base, spec and contract snapshot. The earlier G1 report’s prefix discrepancy remains unexplained; this fresh review supplies independent current evidence. Recompute these hashes before accepting G1 and before G2. A changed spec, authority/ownership prefix, Plan contract, branch/base/plan identity, instruction/dependency contract, or unexpected candidate path/mode invalidates this G1 result. Intended progress/check-result updates require inspection at later gates and do not alone invalidate it.
