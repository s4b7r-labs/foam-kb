# Agent instructions

Start with [README.md](README.md).

This repository is the **public** knowledge base. Treat everything committed here as intentionally published information.

## KB landscape and publication routing

There are three distinct KB repositories:

- [`s4b7r-ianus/kb`](https://github.com/s4b7r-ianus/kb) — IANUS-local work KB; work-specific IP stays there among the three KBs;
- [`s4b7r-labs/foam-kb-private`](https://github.com/s4b7r-labs/foam-kb-private) — private personal KB for non-work personal or non-public knowledge;
- [`s4b7r-labs/foam-kb`](https://github.com/s4b7r-labs/foam-kb) — this public personal KB, for knowledge intentionally suitable for publication.

When the user asks to add, store, record, or update something in "my KB" or similar wording without explicitly naming public or private:

1. Work-specific, employer-derived, customer-derived, project-specific, or plausibly work-confidential material belongs in the work KB, never here.
2. Write here only when there is reasonably strong confidence that publication is intended and the material is suitable for public disclosure.
3. Prefer the private personal KB for non-work personal, contextual, potentially sensitive, or not-clearly-public material.
4. If provenance, IP ownership, or publication intent is materially ambiguous, do not publish.
5. Never copy from the private personal KB or work KB merely because the material would be useful here; publication requires its own justification.
6. Work-derived material may appear here only as a deliberately safe, self-contained abstraction with no employer/customer/project-specific IP.
7. An explicit user instruction naming this KB still does not override confidentiality, IP, or publication constraints.

This routing rule applies before any content write. Do not silently duplicate or synchronize material across KBs.

## Knowledge maintenance

Before adding durable knowledge:

1. Search for an existing related note.
2. Update an existing canonical note when that is the clearer result.
3. Otherwise create the smallest useful new note.
4. Link new material from an existing relevant note or from `README.md` when it is a primary entry point.
5. Preserve unresolved questions explicitly rather than inventing answers.
6. Avoid introducing structure, schemas, generated indexes, or automation without demonstrated need.

Files, folders, and Markdown links are the source of truth. Prefer standard relative Markdown links in operational files intended to work both on GitHub and across different agents.
