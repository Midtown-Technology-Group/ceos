# CEOS

This fork owns Claude Code EOS skills and templates, plus company-specific Markdown data where populated. Read [README.md](README.md) for the three-layer model and [CONTRIBUTING.md](CONTRIBUTING.md) before changes. `skills/ceos-*/SKILL.md` contains workflows, `templates/` supplies starter documents, `data/` holds company records, and `setup.sh` installs/initializes them.

Keep upstream skill/template improvements separate from private company data and personal `.ceos-user.yaml` configuration. Do not include leadership, personnel, financial, or company record contents in public examples, upstream PRs, or logs. Inspect only the records relevant to the assigned work. Do not invent owners, commitments, scores, or meeting outcomes; distinguish recommendations from approved EOS records.

Templates are additive only: never remove or rename existing templates. Frontmatter keys and status values form a data contract. Optional additions need documentation; breaking changes require RFC-style issue discussion and a major version bump. Skill names/triggers need prior issue discussion; every skill change requires the contributing guide's security review. Skills stay within their own file and relevant `data/`/`templates/`, show a diff before writing, include Guardrails, and must not handle credentials, make external calls, execute arbitrary shell commands, or auto-invoke other skills. Keep the `setup.sh` interface backward compatible.

For skill changes, provide before/after examples and verify installation using the contributing guide's `./setup.sh` procedure in an isolated copy. `./setup.sh init` initializes company data and must not be run against existing company records merely as a test. Dashboard CI installs cryptography/pytest and runs `python -m pytest tests/test_build.py -v`; use that seam for dashboard behavior. Report checks actually executed separately from documented commands.

New EOS workflows need an issue/design discussion first. Keep one concern per PR, update affected docs, and retain maintainer review before merge. Review dashboard build/publishing configuration before any command that could publish company information.
