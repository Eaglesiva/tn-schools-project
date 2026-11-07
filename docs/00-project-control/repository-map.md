# TN Schools — Repository Map

**Last checked:** 2026-11-07 (Asia/Kolkata)

## Repository roles

| Range | Purpose | Keep in these repositories |
|---|---|---|
| `tn-class-01` … `tn-class-12` | Current class production | Current approved textbook edition, matching page index/viewer data, Book-back questions, verified one-mark answers, quiz files and class-specific runtime assets |
| `tn-class-01-archive` … `tn-class-12-archive` | Historical editions | Superseded textbook editions, old page sets and their historically associated question/answer/quiz data where useful |
| `tn-schools-project` | Common project control | Common blueprint, workflow, templates, quality rules, edition register, cross-class progress, audit evidence index and branch migration register |

## Golden rules

1. `main` is the intended final branch for current class repositories and archive repositories.
2. A branch is not assumed to be current merely because its name contains `official`, `audit`, or a year. Verify its content and its source.
3. Printed imprint year and academic distribution year are separate fields. A 2026–27 official issue can still show a 2018/2019 first-edition imprint on page 2.
4. Page 2 is a required evidence link, but page 2 alone does not prove that two complete books are identical. Also check official source, total pages, TOC, full-page/content comparison and split integrity.
5. Do not delete a branch, file, old book, quiz, answer, workflow or source evidence until its useful contents have been copied, cross-checked and linked here.
6. Never replace a production book until viewer routing, `pages.json`, chapter boundaries, Book-back question mapping and Cloudflare output have been checked.
7. Keep all source URLs, GitHub paths, commit SHA, Page-2 PDF link and audit record in the Edition Register.

## Source paths

- Common blueprint: [docs/01-blueprint](../01-blueprint/)
- Common workflow: [docs/02-workflow](../02-workflow/)
- Edition register: [docs/03-edition-register](../03-edition-register/)
- Quality and deployment rules: [docs/04-quality-control](../04-quality-control/)
- Templates: [docs/05-templates](../05-templates/)
- Branch and migration records: [docs/06-migration-control](../06-migration-control/)
- Audit evidence: [docs/07-audit-evidence](../07-audit-evidence/)

## Cloudflare boundary

This repository does not become a Pages production source. Common documents and audit records belong here. Pages projects must deploy only the website's intended build output. A Git branch or a GitHub folder is not automatically safe to deploy. See [Cloudflare deployment policy](../04-quality-control/CLOUDFLARE_DEPLOYMENT_POLICY.md).
