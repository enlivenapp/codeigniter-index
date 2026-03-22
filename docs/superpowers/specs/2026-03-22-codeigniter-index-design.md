# CodeIgniter Index — Design Spec

## Overview

A comprehensive, version-organized catalog of all known third-party packages, libraries, tools, and resources ever built for the CodeIgniter PHP framework. Hosted as a public GitHub repository (`codeigniter-index`) with a simple flat folder structure.

## Goals

- Provide an exhaustive directory of everything built for CodeIgniter across all versions (v1–v4)
- Organize by version so users find what's relevant to them immediately
- Use a table-based format for scannability over traditional bullet lists
- Cross-reference packages that span multiple CI versions
- Include all categories even when empty, to signal what contributions are welcome
- Be the definitive resource for the CodeIgniter ecosystem

## Project Structure

```
codeigniter-index/
├── README.md          # Project overview, CI history/timeline, version status table, contributing guide
├── LICENSE            # MIT License
├── v1/
│   └── README.md      # Discontinued notice, brief history, pointer to newer versions
├── v2/
│   └── README.md      # Discontinued notice, brief history, pointer to newer versions
├── v3/
│   └── README.md      # Full categorized table listing of all known packages/resources
└── v4/
    └── README.md      # Full categorized table listing of all known packages/resources
```

## Root README

Contains the following sections in order:

1. **Title & description** — what this project is and why it exists
2. **Version status table** — quick-reference showing each version, its status (discontinued/maintenance/active), and a link to its subfolder README
3. **CodeIgniter history/timeline** — narrative of the framework's evolution across versions (to be co-authored with user's firsthand knowledge)
4. **How to contribute** — guidelines for adding or updating entries
5. **License** — MIT

## v1 and v2 READMEs

Minimal pages containing:

- Title with version number
- Status notice clearly marked as "Discontinued"
- Brief blurb (1-2 sentences) on what the version was and roughly when it was active
- Pointer/links to v3 and/or v4 as recommended active versions
- Any known surviving archived resources (if any exist; otherwise just the discontinuation notice)

v1 will be nearly empty as it has essentially vanished from the internet. v2 may have a handful of legacy items.

## v3 and v4 READMEs — Entry Format

Each category is presented as a markdown table:

```markdown
## Authentication

| Package | Description | Status | |
|---------|-------------|--------|-|
| [Ion Auth](https://github.com/.../releases/tag/v3.x) | Simple and lightweight auth system | Active | [Newer Available](../v4/README.md#authentication) |
| [Tank-Auth](https://github.com/.../releases/tag/v2.0) | Authentication library | Archived | - |
```

### Column definitions

- **Package** — linked name pointing to the correct release/version for that CI version on GitHub (or homepage if not on GitHub)
- **Description** — one-line summary of what it does
- **Status** — Active, Maintained, Archived, or Unmaintained
- **Cross-reference (unlabeled column)** — "Newer Available" (in v3, linking to `../v4/README.md#category`) or "Older Available" (in v4, linking to `../v3/README.md#category`), or `-` if single-version only. Links use GitHub-compatible markdown header anchors.

## Categories

All categories listed in every v3/v4 README, even if empty. Empty categories display:

```markdown
## Payment Gateways

*No packages found for this version. [Contribute one?](link-to-contributing)*
```

### Category List

**Core & Framework**
- Boilerplates / Starters
- Modular Extensions (HMVC, etc.)
- CLI Tools

**Authentication & Authorization**
- Authentication
- Authorization / ACL

**Database & ORM**
- ORM / Active Record Extensions
- Migrations
- Database Tools

**Content & Admin**
- CMS
- CRUD Generators
- Admin Panels

**API & Web Services**
- REST Server / Client
- Payment Gateways
- Social Media Integrations

**Frontend & Templating**
- Template Engines
- Asset Management

**Development & Testing**
- Debugging / Profiling
- Testing
- Code Generators

**AI & Automation**
- AI/LLM Skills & Integrations
- Code Generation Tools

**Utilities**
- Caching
- Email
- File Handling
- Search
- Geolocation
- Security / Encryption
- Breadcrumbs / Navigation
- Internationalization

**Resources**
- Tutorials & Guides
- User Guide Translations
- Community

## Research & Population Strategy

Goal is exhaustive coverage from the initial release. Sources to mine:

1. **Known aggregators** — the [awesome-codeigniter](https://github.com/codeigniter-id/awesome-codeigniter) repo, Packagist, archived CodeIgniter Sparks registry
2. **GitHub search** — repos tagged/titled with codeigniter, codeigniter3, codeigniter4, CI3, CI4
3. **Packagist/Composer** — packages in the `codeigniter4/*` namespace and those requiring `codeigniter/framework` or `codeigniter4/framework`
4. **Community sources** — CodeIgniter forum, official website resources page, Stack Overflow tags
5. **Validation** — confirm each entry exists, check if archived/maintained, find correct release links for the right CI version
6. **User knowledge** — fill gaps especially for v1/v2 history and anything automated research misses

## License

MIT
