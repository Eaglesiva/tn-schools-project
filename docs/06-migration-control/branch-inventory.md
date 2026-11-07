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