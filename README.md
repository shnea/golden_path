# Golden Path

[한국어](README.ko.md) · [English skill](en/SKILL.md) · [한국어 스킬](ko/SKILL.md)

A skill for maintaining a project's current development standards and the skills used to build it, in a document people can read and review.

The Golden Path explains which technologies, structure, and working rules apply to a project. A separate skills table helps the next person understand which skills contributed to the result and what each was used for.

Agents can look up relevant entries when needed. This skill does not require them to read the document before every development task or keep it in their ongoing context.

## What it maintains

- Development standards: languages, frameworks, package managers, folder structure, naming conventions, coding rules, testing rules, and constraints.
- Skills used in development: each skill's actual name and a short description of its function and application in the project.

The document contains the current standards, rather than a history of decisions or changes. It does not collect conversation summaries or progress logs. Undecided standards remain `Undecided`; installed but unused skills are not listed.

## Choose a language

```text
golden_path/
├── README.md
├── README.ko.md
├── en/
│   └── SKILL.md
└── ko/
    └── SKILL.md
```

Both versions define the same `golden-path` skill. Install one language version as `golden-path/SKILL.md` in your tool's skills directory.

## Installation

### Codex: personal installation

Clone this repository, then copy the English entrypoint and license into your personal skills directory:

```sh
git clone https://github.com/shnea/golden_path.git
cd golden_path
mkdir -p "$HOME/.agents/skills/golden-path"
cp en/SKILL.md LICENSE "$HOME/.agents/skills/golden-path/"
```

For Korean, use `ko/SKILL.md` as the source instead. If you already have a `golden-path` skill, compare it before replacing it.

### Codex: project installation

From the target project's root, copy your chosen entrypoint from your local clone:

```sh
mkdir -p .agents/skills/golden-path
cp /path/to/golden_path/en/SKILL.md /path/to/golden_path/LICENSE .agents/skills/golden-path/
```

Replace `/path/to/golden_path` with the actual path to your clone. Codex discovers these personal and project skill locations; see the [official skills documentation](https://learn.chatgpt.com/docs/build-skills).

### Other tools

For a tool that supports `SKILL.md` skills, place the selected file in that tool's documented skills directory as `golden-path/SKILL.md`, with a copy of `LICENSE` alongside it. Installation paths and invocation syntax depend on the tool.

## Usage

In Codex, invoke `$golden-path` with a request such as:

```text
$golden-path Help me define this project's development standards.
Leave anything we haven't agreed on as Undecided.
```

```text
$golden-path Show the current development standards and skills used in this project.
```

```text
$golden-path Set the package manager to pnpm and add skill-creator to the skills table.
It was used to review the skill's scope and write its SKILL.md instructions.
```

When the agent proposes an addition or change, it shows the proposed content and asks for agreement before saving it. A specific user request to apply a change already provides that agreement.

## Generated document

The default output is `docs/GOLDEN_PATH.md` in the project being worked on. A user-specified or project-defined path takes priority; otherwise an existing Golden Path document is reused.

The following is an illustrative document, not a set of required technologies or skills. Actual entries should reflect agreed project standards and verified skill use.

```markdown
# Golden Path

## Development standards

| Item | Applicable standard |
| --- | --- |
| Language | TypeScript |
| Package manager | pnpm |
| Naming conventions | Undecided |

## Skills used in development

| Skill name | Role description |
| --- | --- |
| skill-creator | Reviews skill scope and instructions; used to structure and refine SKILL.md. |
```

Changed standards replace their relevant entries. Each skill occupies one row, with its role updated as needed; execution dates, invocation counts, and task logs are not accumulated.

## Contributing

Keep `en/SKILL.md` and `ko/SKILL.md` aligned when changing behavior. Preserve the focus on a document for people to review, current development standards, actual skill use, and user-approved changes.

## License

[MIT](LICENSE).
