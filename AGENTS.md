# Agent instructions

Start with [README.md](README.md).

This repository is the **public** knowledge base. Treat everything committed here as intentionally published information.

## Public vs. private knowledge

There are two related KB repositories:

- `s4b7r/foam-kb-private` — private, and the canonical destination for personal or non-public knowledge;
- `s4b7r-labs/foam-kb` — this public KB, for knowledge that is intentionally suitable for publication.

When the user asks to add, store, record, or update something in "my KB" or similar wording without explicitly naming public or private:

1. Determine whether the material is clearly appropriate for the public KB or should remain private.
2. Write here only when there is reasonably strong confidence that publication is intended and the material is suitable for public disclosure.
3. Prefer the private KB when the material is personal, contextual, potentially sensitive, or simply lacks a clear reason to be public.
4. If the correct destination is materially ambiguous, ask the user whether it should be public or private before writing.
5. Never copy or derive information from the private KB into this repository merely because it would be useful here; publication requires its own justification or explicit user intent.
6. An explicit user instruction naming one of the KBs overrides inference about destination, subject to normal safety and privacy constraints.

This routing rule applies before any content write. Do not silently duplicate new material into both KBs unless the user explicitly asks for both copies or there is a clearly established synchronization rule for that material.

## Knowledge maintenance

Before adding durable knowledge:

1. Search for an existing related note.
2. Update an existing canonical note when that is the clearer result.
3. Otherwise create the smallest useful new note.
4. Link new material from an existing relevant note or from `README.md` when it is a primary entry point.
5. Preserve unresolved questions explicitly rather than inventing answers.
6. Avoid introducing structure, schemas, generated indexes, or automation without demonstrated need.

Files, folders, and Markdown links are the source of truth. Prefer standard relative Markdown links in operational files intended to work both on GitHub and across different agents.
