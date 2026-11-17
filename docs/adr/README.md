# Architecture Decision Records (ADRs)

- This folder contains decisions made in the project.
- Each ADR file should be named with a four-digit sequential **number** and a short title, separated by hyphens (kebab-case), for
  example,
  `0001-use-csharp-for-backend.md`.
- The title describes the decision, usually starting with a verb, for example `Use ... for ...`.
- Each ADR file must contain context, decision, rejected alternatives and consequences.
- Each ADR file must contain a status such as `Proposed`, `Accepted`, `Rejected ...`
    - When a decision changes, we don't modify the old ADR file. We create a new ADR file, and the status of the old one
      becomes `Superseded by 00XX`
    - Why? To keep the history of the reasoning.
