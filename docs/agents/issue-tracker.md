# Issue tracker: Local Markdown

Issues and specs live as Markdown files in `.scratch/`.

## Conventions

- One feature per directory: `.scratch/<feature-slug>/`.
- Spec: `.scratch/<feature-slug>/spec.md`.
- Implementation tickets: `.scratch/<feature-slug>/issues/<NN>-<slug>.md`,
  numbered from `01`, one file per ticket.
- Triage state: a `Status:` line near the top of each issue file,
  using the roles in `triage-labels.md`.
- Comments: append under a `## Comments` heading.

## Publish or fetch work

To publish, create the corresponding spec or ticket file, creating
directories as needed. To fetch, read the referenced file.

## Wayfinding operations

- Map: `.scratch/<effort>/map.md`, with Notes, Decisions-so-far, and Fog.
- Child tickets: `.scratch/<effort>/issues/NN-<slug>.md`.
- Record `Type:` as research, prototype, grilling, or task.
- Use `Status: open`, `Status: claimed`, or `Status: resolved`.
- Record dependencies as `Blocked by: NN, NN`.
- A ticket is unblocked when every listed dependency is resolved.
- Frontier: open, unblocked, unclaimed tickets, lowest number first.
- Claim: save `Status: claimed` before starting work.
- Resolve: append an `## Answer`, save `Status: resolved`, and append
  a summary and ticket link to the map's Decisions-so-far.
