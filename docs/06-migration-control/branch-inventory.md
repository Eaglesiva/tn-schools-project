# Branch Inventory — Before Consolidation

**Checked:** 2026-11-07 18:30 IST (live GitHub branch listing)  
**Scope:** `Eaglesiva/tn-class-01` through `tn-class-12`. The branch search continuation cursors were exhausted for all 12 repositories.  
**Policy:** Preserve all listed branches until their unique files have been catalogued, copied and verified. The inventory is a snapshot; re-check immediately before any branch mutation.

| Repository | Non-main branches currently found | Initial role / handling |
|---|---|---|
| `tn-class-01` | `scert/class-01/audit-2026-27-term1-vol1` | Edition audit, official 2026 Term I/II splits, manifests and evidence; preserve while migrating evidence and reviewing combined-book TOC |
| `tn-class-02` | `scert/class-02/audit-2026-27` | Edition audit, official 2026 Term I/II splits and evidence; preserve |
| `tn-class-03` | `scert/class-03/audit-2026-27` | Edition audit, official 2026 Term I/II splits and evidence; preserve |
| `tn-class-04` | `scert/class-04/audit-2026-27` | Edition audit, official 2026 Term I splits and evidence; preserve |
| `tn-class-05` | `scert/class-05/audit-2026-27` | Edition audit, official 2026 Term I splits and evidence; preserve |
| `tn-class-06` | `scert/class-06/audit-2026-27` | Edition audit, official 2026 Term I splits and evidence; preserve |
| `tn-class-07` | `scert/class-07/audit-2026-27` | Edition audit, official 2026 Term I splits and evidence; preserve |
| `tn-class-08` | `scert/class-08/audit-2026-27` | Edition audit, 2026–27 full-year official splits and evidence; preserve |
| `tn-class-09` | `scert/class-09/audit-2026-27`; `scert/refresh/class-09` | Edition audit and separate refresh evidence; preserve both until reviewed |
| `tn-class-10` | `content/class10-tamil-iyal1-answer-guide-2026-11-05`; `content/class10-tamil-iyal1-answers-quiz-2026-11-04`; `feature/scert-edition-pilot`; `scert/class-10/audit-2026-27`; `scert/class-10/official-version-updates`; `scert/master-edition-tracking`; `scert/refresh/class-10` | Contains recent Tamil answers/quiz work, edition pilot, audit, official version splits, master tracker and refresh evidence; none may be deleted or bulk-merged |
| `tn-class-11` | `scert/class-11/audit-2026-27`; `scert/class-11/official-version-updates` | Contains audit and 2026–27 official edition sets; preserve |
| `tn-class-12` | `scert/class-12/audit-2026-27`; `scert/class-12/official-version-updates`; `scert/refresh/class-12` | Contains audit, official update sets and refresh evidence; preserve |

## Live inventory result

- All 12 current class repositories have a `main` branch.
- Classes 1–8 each currently show one non-main SCERT audit branch.
- Class 9 shows two non-main branches.
- Class 10 shows seven non-main branches, including two active Tamil content branches that must be reconciled separately from edition work.
- Class 11 shows two non-main branches.
- Class 12 shows three non-main branches.
- Common repository `tn-schools-project` currently shows only `main`.
- Total observed current-class branches: 12 `main` + 22 non-main = 34 branches. This count excludes the 12 archive repositories.

## Consolidation rule

The final state should use `main` as the active branch, but the transition must be staged:
1. Copy and verify unique evidence in this common repository.
2. Copy class-specific working documents to the matching class repository's `docs/` folder.
3. Move the correct current official book/page set into the production location only after Edition Gate and viewer checks.
4. Copy superseded book/page sets and associated historical question data to the matching Archive repository.
5. Verify GitHub links, `pages.json`, viewer behavior and Cloudflare deployment.
6. Only after these checks, decide whether each historical working branch can be closed/deleted.

**No branch was deleted or merged by this inventory.**

## Document migration map — inspected branches

| Branch family | Document classification | Destination copied to | Remaining branch-only material / hold |
|---|---|---|---|
| Classes 1–8 `scert/class-XX/audit-2026-27` | Class-specific audit manifest and summary | Each matching class `main/docs/edition-audit/2026-27/` | Official edition page splits and source audit workflow remain on audit branches pending Edition Gate / viewer mapping |
| Class 9 `scert/class-09/audit-2026-27` | Class 9 manifest, summary and Page-2 comparison | Class 9 `main/docs/edition-audit/2026-27/` | Official edition source assets remain on audit branch pending production decision |
| Class 9 `scert/refresh/class-09` | Five subject refresh evidence JSON files | Class 9 `main/docs/edition-audit/2026-27/refresh_evidence/` | Refreshed book assets remain on branch until comparison and deployment checks |
| Class 10 content branches (two Tamil Iyal 1 branches) | Shared/global blueprint and audit snapshots; Class 10 Tamil diff and answer/quiz work | Shared records copied to Common; Class 10 diff copied to Class 10 `main/docs/edition-audit/2026-27/` | Actual answer/quiz content changes remain isolated in their content branches pending QA |
| Class 10 `feature/scert-edition-pilot` | Pilot edition assets; duplicated shared docs | Shared docs centralized in Common; class-specific evidence preserved in Class 10 | Pilot page assets remain isolated; no production promotion |
| Class 10 `scert/master-edition-tracking` | Cross-class master tracker, index CSV, audit status, global evidence and working blueprint | Common `docs/07-audit-evidence/master-edition-tracking-2026-11-05/` | Class 10 maths visual/verification evidence copied to Class 10 main; original branch preserved pending full branch retirement review |
| Class 10 `scert/refresh/class-10` | Class 10 English refresh evidence | Class 10 `main/docs/edition-audit/2026-27/refresh_evidence/` | Refreshed English page assets remain on refresh branch pending comparison |
| Class 10 `scert/class-10/official-version-updates` | Shared master audit reports plus Class 10-specific diff / official update report | Shared reports copied to Common; Class 10-specific reports copied to Class 10 main | Official Science/Social Science split assets remain on update branch pending full content comparison |
| Class 11 `scert/class-11/official-version-updates` | Class 11 verification report and batch 1–4 reports | Class 11 `main/docs/edition-audit/2026-27/` | Official 2024 split books remain on update branch pending per-book comparison |
| Class 12 `scert/refresh/class-12` | Aggregate refresh evidence for all refreshed books | Class 12 `main/docs/edition-audit/2026-27/refresh_evidence/` | Individual page assets remain on refresh branch pending edition reconciliation |
| Class 12 `scert/class-12/official-version-updates` | Class 12 verification and cloud update reports | Class 12 `main/docs/edition-audit/2026-27/` | Official split books remain on update branch pending per-book comparison |

## Branch retirement gate

A branch may be considered for deletion only after:
1. Every unique Markdown / CSV / JSON / image evidence file is copied or intentionally retained in the class repository.
2. The copied file hashes / content are verified against the source branch.
3. All page assets have a final CURRENT / ARCHIVE / PENDING decision.
4. GitHub Pages viewer paths and `pages.json` are reconciled.
5. Cloudflare production and Preview deployment settings are verified.
6. The user approves retirement of the branch.

No branch has been deleted or merged in this consolidation pass.
