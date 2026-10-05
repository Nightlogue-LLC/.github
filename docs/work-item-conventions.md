# Nightlogue Work Item Conventions

## Title format

Use:

`[Area] Verb + outcome`

Examples:

- `[Shelf] Add cover stat display preference`
- `[Taxonomy] Create Content Note landing pages`
- `[Navigation] Fix mobile menu overflow`
- `[Recommendations] Explore personalized recommendations`

## Rules

1. Start with one approved Area in square brackets.
2. Follow the Area with an action verb.
3. Describe the desired outcome rather than only naming the problem.
4. Do not repeat metadata already represented by GitHub fields. Product, Type, Priority, and Horizon do not belong in the title.
5. Keep the title concise enough to scan easily on the Nightlogue Command Center.
6. Use `Explore` or `Investigate` when the outcome is intentionally unknown.

## Preferred action verbs

Add · Automate · Create · Explore · Fix · Investigate · Migrate · Refactor · Remove · Standardize · Update

This is guidance, not a closed verb vocabulary.

## Controlled Area vocabulary

### Forbidden Folio

- `[Shelf]` — reader shelf/library and shelf-card experiences
- `[Book Guides]` — public book-guide pages and guide-specific presentation
- `[Catalog]` — book records, metadata, series data, and catalog management
- `[Taxonomy]` — canonical terms, tags, content notes, heat/darkness terminology, and term pages
- `[Quiz]` — Forbidden Folio quiz and result experiences
- `[Search]` — in-product search, discovery, filtering, and retrieval
- `[Journal]` — journal/reading-log experiences
- `[Account]` — reader account, profile, authentication, and preferences
- `[Navigation]` — global navigation and wayfinding
- `[Admin]` — internal editorial/admin tooling
- `[SEO]` — search-specific implementation and organic-search work
- `[Infrastructure]` — technical foundations, integrations, deployment, and developer tooling

### ExactMods

- `[Fitment]`
- `[Catalog]`
- `[Guides]`
- `[Search]`
- `[Vehicles]`
- `[Parts]`
- `[SEO]`
- `[Admin]`
- `[Infrastructure]`

### Other Nightlogue products

Define a product's Area vocabulary here before treating new Area names as canonical. Reuse an existing Area when its meaning is genuinely the same; do not force products into identical vocabularies when their product surfaces differ.

## Metadata ownership

Titles answer: **where inside the product + what is changing?**

GitHub fields answer the rest:

- **Product** — which Nightlogue product owns the work
- **Type** — Task, Bug, Feature, Improvement, Content, SEO, Maintenance, Research, or Idea
- **Horizon** — Now, Soon, Later, or Someday
- **Priority** — current importance
- **Status** — workflow state in the Nightlogue Command Center

Avoid titles such as `[Bug] Shelf cards don't show darkness`, `[FF] SEO stuff`, or `High Priority - Fix nav`.

## Parent and sub-issue naming

Parent issues use the same convention. Sub-issues name their own concrete outcome rather than repeating the parent's title.

Parent: `[Book Guides] Unify Heat and Darkness scale UI`

Child: `[Shelf] Add cover stat display preference`

The relationship carries the hierarchy; the title should remain useful when viewed by itself.
