# Contributing to Decklog

Decklog is a research-stage project: there is no runtime to patch, no experiment harness to extend, and no benchmark to beat yet. Contributions at this stage are research contributions.

## How to contribute now

- **Ask or refine a research question.** Open a [research proposal issue](https://github.com/ahwlsqja/decklog/issues/new/choose) or comment on an existing one. The current open questions live in [docs/research/questions.md](docs/research/questions.md).
- **Bring evidence, not assertions.** Cite prior work by its original source (paper, pinned documentation revision, repository commit) rather than summaries of summaries. If you ran something, make it reproducible: describe the setup, inputs, and how a reader could repeat it.
- **Critique the hypotheses.** The claims in [README.md](README.md) are hypotheses, not results. Pointing at a case where the assumed cost or benefit does not hold is a contribution.
- **Discuss in the open.** All research discussion happens in [GitHub issues](https://github.com/ahwlsqja/decklog/issues) on this repository so conclusions stay linked to the record.

## What is not ready yet

- Runtime code, agent implementations, and the experiment harness do not exist yet. Substantial proposals for them are welcome — open an issue first that states the research question, the scope, and the evaluation plan so the approach can be discussed before code is written.
- Performance, cost, or reliability claims (ours or comparisons against other systems) are unverified until the planned evaluation exists. Please don't add numbers the repository cannot reproduce.
- Documentation corrections and clarifications are welcome.

## Commit conventions

Commits follow the project's Lore protocol:

- The subject states **why** the change exists; an optional concise body covers the what/how.
- Add git trailers only when they carry useful information:
  - `Constraint:` — a limit the change works within
  - `Rejected:` — an alternative set aside and why, as `alternative | reason`
  - `Confidence:` — `low`, `medium`, or `high`
  - `Scope-risk:` — `narrow`, `moderate`, or `broad`
  - `Directive:` — a forward-looking warning for future modifiers
  - `Tested:` / `Not-tested:` — how the change was or was not verified

## License

By contributing, you agree your contributions are licensed under the repository's [Apache-2.0 license](LICENSE).
