# @openhint/hintbook-procurement-specialist

This package supports procurement documentation and requires review by the procurement authority.

The official [HINT](https://github.com/open-hint-dev/hint) vocabulary for procurement. The assistant drafts vendor-neutral tender text; it never invents budgets or exposes internal scoring weights.

Measured performance and retrieval results live in the core [benchmark report](https://github.com/open-hint-dev/hint/blob/main/docs/09-benchmarks.md).

```
hint.yml
_.hint
monorail/
├── _.hint
└── artifact.md.hint
tire-fire-cleanup/
└── _.hint
shared/policy.hint
```

## Installation

```bash
hint add @openhint/hintbook-procurement-specialist
hint apply
```

## Vocabulary

| Tender | `tender`, `need`, `budget`, `timeline`, `contact`, `process` |
| Requirements | `requirement`, `exclusion`, `question`, `deliverable`, `sla` |
| Evaluation | `criterion`, `weight`, `scale`, `panel`, `conflict` |
| Shared core | `never`, `source`, `term`, `assumption`, `risk`, `decision`, `openquestion`, `checklist`, `style`, `example`, `good`, `bad`, `read`, `res`, `notes` |

Natural plurals and long forms are included as keyword synonyms; profession search synonyms are declared in `keywords/hintbook.json`. Full reference: [docs/keywords.md](docs/keywords.md).

## Output and framing

| Command | Result |
| --- | --- |
| `hint <path>` | Scoped profession knowledge only. |
| `hint --prompt <path>` | Role header, scoped knowledge, verification footer. |
| `hint --standalone <path>` | Prompt plus the complete tag glossary. |

Verifiable surfaces: `requirement`. These names are stable artifact identifiers and must appear verbatim.

## Deterministic emit

The markdown pack emits reviewable procurement document structure without a model. Run `hint emit <path>` and gate CI with `hint emit --check`. Prose that templates cannot derive remains a marked hole.

Internal positions — `criterion`, `weight`, `scale`, `panel` — deliberately have no emit template. They constrain the work and never leak into the published artifact.

## Example

```markdown
# tender monorail

Declared context for the procurement document.

# never Invented details

The assistant drafts vendor-neutral tender text; it never invents budgets or exposes internal scoring weights.
```

## Disclaimer

This package supports procurement documentation and requires review by the procurement authority.

## License

MIT
