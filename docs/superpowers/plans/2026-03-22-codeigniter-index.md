# CodeIgniter Index Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Create a comprehensive, version-organized catalog of all known CodeIgniter packages, libraries, tools, and resources as a GitHub-ready repository.

**Architecture:** Flat folder structure with a root README (overview, history, links, contributors), per-version subfolders each containing a single README with categorized tables. CONTRIBUTING.md and LICENSE at root. Content populated through exhaustive research across Packagist, GitHub, community sources, and user knowledge.

**Tech Stack:** Markdown, Git

**Spec:** `docs/superpowers/specs/2026-03-22-codeigniter-index-design.md`

---

### Task 1: Project Scaffolding — LICENSE and CONTRIBUTING.md

**Files:**
- Create: `LICENSE`
- Create: `CONTRIBUTING.md`

- [ ] **Step 1: Create MIT LICENSE file**

Create `LICENSE` with MIT license text, copyright holder "CodeIgniter Index Contributors", year 2026.

- [ ] **Step 2: Create CONTRIBUTING.md**

Create `CONTRIBUTING.md` with the following sections:

```markdown
# Contributing to CodeIgniter Index

## Adding a New Entry

Every entry requires all four table columns:

| Column | What to provide |
|--------|----------------|
| Package | Package name linked to the correct release for that CI version (tagged release preferred, branch if no tags, repo root as fallback) |
| Description | One-line summary of what the package does |
| Status | One of: Active, Maintained, Archived, Unmaintained (see definitions below) |
| Also Available | Link to the entry in another version's README if applicable, or `-` |

## Status Definitions

- **Active** — regular commits in the last 12 months, accepting issues/PRs
- **Maintained** — stable, receives security/compatibility fixes but no new features
- **Archived** — repo explicitly archived by owner or marked as end-of-life
- **Unmaintained** — no meaningful activity for 2+ years, not explicitly archived

## Pull Request Format

- One entry per PR preferred, or batch additions within a single category
- Entries must be placed in alphabetical order within their category table
- Verify the package exists and the link resolves before submitting

## Proposing New Categories

Open an issue describing the category and at least one package that would belong in it.
```

- [ ] **Step 3: Commit**

```bash
git add LICENSE CONTRIBUTING.md
git commit -m "Add MIT license and contribution guidelines"
```

---

### Task 2: v1 and v2 READMEs — Discontinued Versions

**Files:**
- Create: `v1/README.md`
- Create: `v2/README.md`

- [ ] **Step 1: Create v1/README.md**

```markdown
# CodeIgniter v1

> **Discontinued** — CodeIgniter v1 is no longer available. Source code and documentation have been removed from public distribution.

CodeIgniter v1 was the original release of the framework, first appearing in 2006 by EllisLab. It established the lightweight MVC pattern that CodeIgniter became known for.

No known packages, libraries, or resources survive for this version.

## Looking for active versions?

- [CodeIgniter v3](../v3/README.md) — security-only maintenance mode
- [CodeIgniter v4](../v4/README.md) — actively developed
```

Note: The history details (dates, specifics) will need user input to verify/expand. Use placeholder content and flag for review.

- [ ] **Step 2: Create v2/README.md**

```markdown
# CodeIgniter v2

> **Discontinued** — CodeIgniter v2 is no longer supported or maintained.

CodeIgniter v2 was released in 2011, introducing improvements over v1 including better Active Record, a query builder, and improved documentation.

## Known Resources

Any surviving v2-specific packages or resources will be listed here as they are found.

*No packages currently cataloged for this version. [Contribute one?](../CONTRIBUTING.md)*

## Looking for active versions?

- [CodeIgniter v3](../v3/README.md) — security-only maintenance mode
- [CodeIgniter v4](../v4/README.md) — actively developed
```

Note: Same as v1 — history details need user verification. v2 may get entries added later if legacy packages are discovered during research.

- [ ] **Step 3: Commit**

```bash
git add v1/README.md v2/README.md
git commit -m "Add v1 and v2 discontinued version READMEs"
```

---

### Task 3: v3 README — Category Structure

**Files:**
- Create: `v3/README.md`

- [ ] **Step 1: Create v3/README.md with all category tables**

Build the full v3 README with:
- Title and maintenance mode notice at top
- Table of contents linking to all category sections
- Every category from the spec as an `## H2` section
- Each category containing either a populated table or the "No packages found" placeholder
- Tables use the format: `| Package | Description | Status | Also Available |`

Categories to include as H2 sections (in this order):

1. Boilerplates / Starters
2. Modular Extensions
3. CLI Tools
4. Authentication
5. Authorization / ACL
6. ORM / Active Record Extensions
7. Migrations
8. Database Tools
9. CMS
10. CRUD Generators
11. Admin Panels
12. REST Server / Client
13. Payment Gateways
14. Social Media Integrations
15. Template Engines
16. Asset Management
17. Debugging / Profiling
18. Testing
19. Scaffolding / CLI Generators
20. AI/LLM Skills & Integrations
21. AI-Powered Code Generation
22. Caching
23. Email
24. File Handling
25. Search
26. Geolocation
27. Security / Encryption
28. Breadcrumbs / Navigation
29. Internationalization
30. Tutorials & Guides
31. User Guide Translations
32. Community

All tables start empty with placeholder text. Content will be populated in Task 5.

- [ ] **Step 2: Commit**

```bash
git add v3/README.md
git commit -m "Add v3 README with category structure"
```

---

### Task 4: v4 README — Category Structure

**Files:**
- Create: `v4/README.md`

- [ ] **Step 1: Create v4/README.md with all category tables**

Same structure as v3 but:
- No maintenance mode notice (v4 is actively developed)
- Title reflects v4
- Cross-references will say "Older Available" pointing to `../v3/README.md#category`

Same 32 categories, all starting empty with placeholder text.

- [ ] **Step 2: Commit**

```bash
git add v4/README.md
git commit -m "Add v4 README with category structure"
```

---

### Task 5: Research & Populate v3 Entries

This is the largest task — exhaustive research to find all CI3 packages.

**Files:**
- Modify: `v3/README.md`

- [ ] **Step 1: Mine the awesome-codeigniter repo**

Go through every entry in https://github.com/codeigniter-id/awesome-codeigniter README. For each entry:
- Verify the link still works
- Determine which category it belongs to in our structure
- Determine status (Active/Maintained/Archived/Unmaintained)
- Find the correct v3-specific release link
- Check if a v4 version exists (for cross-reference)
- Add to v3/README.md in the correct category table, alphabetically

- [ ] **Step 2: Search Packagist for CI3 packages**

Search Packagist for packages requiring `codeigniter/framework`. For each result:
- Check if it's already cataloged from Step 1
- If new, determine category, status, correct link
- Add to v3/README.md

- [ ] **Step 3: Search GitHub for CI3 repos**

Search GitHub for repos tagged/titled with "codeigniter3", "codeigniter", "CI3". Filter for packages/libraries (not applications or forks of the framework itself). For each:
- Check if already cataloged
- If new, categorize, determine status, add to v3/README.md

- [ ] **Step 4: Community and web sources**

Check CodeIgniter forum, official website resources, and other known community sources for additional CI3 packages not yet found.

- [ ] **Step 5: Sort all entries alphabetically within each category**

Review every table in v3/README.md and ensure entries are in alphabetical order by package name.

- [ ] **Step 6: Commit**

```bash
git add v3/README.md
git commit -m "Populate v3 catalog with researched entries"
```

---

### Task 6: Research & Populate v4 Entries

Same research process as Task 5 but for CI4.

**Files:**
- Modify: `v4/README.md`

- [ ] **Step 1: Search Packagist for CI4 packages**

Search Packagist for packages in the `codeigniter4/*` namespace and those requiring `codeigniter4/framework`. CI4 has a stronger Composer ecosystem so Packagist is the primary source.

- [ ] **Step 2: Search GitHub for CI4 repos**

Search GitHub for repos tagged/titled with "codeigniter4", "CI4". Same filtering as Task 5.

- [ ] **Step 3: Check the official CodeIgniter 4 resources**

Review the official CI4 documentation, addins page, and forum for recommended packages.

- [ ] **Step 4: Cross-reference with v3 catalog**

Review every entry in v3/README.md. For packages that have a CI4 version:
- Add the CI4 version to v4/README.md
- Update the v3 entry's "Also Available" column to say `[Newer Available](../v4/README.md#category)`
- Set the v4 entry's "Also Available" column to say `[Older Available](../v3/README.md#category)`

- [ ] **Step 5: Add AI & Automation entries**

Research and add CI4-specific AI/LLM skills and tools, including Claude Code skills for CodeIgniter.

- [ ] **Step 6: Sort all entries alphabetically within each category**

- [ ] **Step 7: Commit**

```bash
git add v3/README.md v4/README.md
git commit -m "Populate v4 catalog and add cross-references to v3"
```

---

### Task 7: Root README

**Files:**
- Create: `README.md`

- [ ] **Step 1: Write root README.md**

Sections in order:

1. **Title & description** — "CodeIgniter Index" with a description of the project's purpose
2. **Links** — links to codeigniter.com, GitHub org, Packagist, official forum, etc.
3. **Version status table:**

```markdown
| Version | Status | Link |
|---------|--------|------|
| v1 | Discontinued | [v1/](v1/README.md) |
| v2 | Discontinued | [v2/](v2/README.md) |
| v3 | Security-only maintenance | [v3/](v3/README.md) |
| v4 | Active development | [v4/](v4/README.md) |
```

4. **CodeIgniter history/timeline** — placeholder section flagged for user co-authoring. Include what is known, mark gaps clearly.
5. **How to contribute** — brief paragraph linking to CONTRIBUTING.md
6. **Contributors** — section for listing contributors and what they contributed (e.g., GitHub username + contribution area)
7. **License** — MIT with link to LICENSE file

- [ ] **Step 2: Commit**

```bash
git add README.md
git commit -m "Add root README with project overview and version index"
```

---

### Task 8: Review & Cross-Reference Validation

**Files:**
- Modify: `v3/README.md` (if needed)
- Modify: `v4/README.md` (if needed)

- [ ] **Step 1: Validate all cross-references**

For every entry with "Newer Available" or "Older Available":
- Verify the link target exists in the other version's README
- Verify the anchor (e.g., `#authentication`) resolves to the correct H2 heading
- Fix any broken or missing cross-references

- [ ] **Step 2: Validate all external links**

Spot-check a sample of package links to confirm they resolve correctly.

- [ ] **Step 3: Review category placement**

Scan for entries that might fit better in a different category or appear to be duplicated across categories.

- [ ] **Step 4: Commit any fixes**

```bash
git add -A
git commit -m "Fix cross-references and validate links"
```

---

### Task 9: User Review — History & Gaps

This task requires human collaboration.

- [ ] **Step 1: Present history/timeline draft for user review**

The root README's history section needs user input. Present what was written and ask for corrections, additions, and firsthand knowledge.

- [ ] **Step 2: Present v1/v2 READMEs for user review**

These are the sparsest pages. Ask user if they know of any surviving v1/v2 resources or can improve the history blurbs.

- [ ] **Step 3: Review overall catalog with user**

Walk through any categories that are sparse or where research was inconclusive. Flag entries where status was uncertain.

- [ ] **Step 4: Commit any user-driven updates**

```bash
git add -A
git commit -m "Incorporate user feedback on history and catalog"
```

---

### Task 10: GitHub Repository Setup

- [ ] **Step 1: Rename default branch to main**

```bash
git branch -m master main
```

- [ ] **Step 2: Create GitHub repository**

```bash
# User will need to create the repo on GitHub first, or use gh cli if available
git remote add origin git@github.com:<username>/codeigniter-index.git
git push -u origin main
```

Note: This step requires the user's GitHub username and may require `gh` CLI or manual repo creation on github.com.

- [ ] **Step 3: Verify rendering on GitHub**

Check that all README files render correctly on GitHub:
- Tables display properly
- Cross-reference anchor links work
- Relative links between folders resolve
