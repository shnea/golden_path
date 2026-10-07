---
description: Maintain a Golden Path so people can review a project's
  technologies, structure, working rules, and skills used in development.
  Use when asked to organize, review, or update project standards. Do not
  use it as a standing reference for ordinary development work.
name: golden-path
license: MIT
---

# Golden Path

Organize and maintain the project's current standards with the user so
people can read and review them. The Golden Path specifies the technologies
in use, project structure, working rules, and major constraints, and lists
the names and roles of skills used in development. It is not a project
overview, long-term conversation memory, or a decision history.

## Audience and Reference Use

-   People are the primary audience. Explain technologies, rules, and
    skills used so people can quickly understand and evaluate them.
-   Agents may look up relevant content when asked to organize, review,
    or update standards, or when a specific standard needs clarification.
-   Do not require agents to read the Golden Path at the start of every
    development task or keep the whole document in their ongoing context.
-   Do not add automatic loading, mandatory references, or required
    pre-task checks to other agent instructions merely because the
    Golden Path exists or changes.
-   Do not make reading, organizing, or updating the document a prerequisite
    for ordinary development. While awaiting approval, defer only the
    document change and do not block independent development work.

## Storage Location and Format

-   Follow a path specified by the user or the project's instructions.
    Otherwise, use an existing Golden Path document if one is present.
-   If no path is specified and no document exists, save it as
    `docs/GOLDEN_PATH.md` in the project being worked on. Create `docs/`
    if needed. Do not save it in the skill's installation folder.
-   Write new documents in Markdown. Use a `Development standards`
    section with an `Item | Applicable standard` table and a
    `Skills used in development` section with a `Skill name | Role description`
    table. When updating an existing document, follow its format.
-   Read existing content before creating or updating the document, and
    apply approved standards to the relevant entries. Do not maintain
    duplicate copies of the same standards across multiple documents.

## Instructions

-   At the beginning of a project, help the user establish applicable
    standards, such as the programming language, framework, package
    manager, folder structure, naming conventions, and major constraints.
-   Include a development standard based on whether it defines how to
    work on the project, rather than how long it will remain relevant.
-   When creating or showing the Golden Path, present it as a table so
    the user can quickly understand and evaluate the standards and skill roles.
-   Do not make undecided choices on the user's behalf. Leave them as
    `Undecided` when appropriate.
-   When proposing a new standard or a change to an existing one during
    a conversation, briefly show the proposed content and obtain the
    user's agreement before adding or updating it. If the user explicitly
    requests a specific addition or update, do not ask for agreement again.
-   When a standard changes, update the relevant entry to keep the
    current standards accurate. Do not accumulate previous standards,
    change logs, or decision-making discussions as a history.
-   Do not include the project's purpose or feature descriptions,
    conversation summaries, work progress, or one-off implementation
    decisions in the Golden Path.
-   Coding style and testing or verification rules may be included when
    they are project standards. Performing implementation, testing, or
    verification work is outside this skill's scope.
-   Never change or remove existing Golden Path standards without the
    user's approval.

## Skills Used in Development

-   List skills actually used in project development in a separate
    section of the same Golden Path document. Do not include a skill
    merely because it is installed or available.
-   Use each skill's actual, identifiable name. Briefly describe what
    the skill does and the work it was used for in the project. Do not
    guess its use or role when these cannot be verified.
-   Keep one row per skill and update its description as needed. Do not
    accumulate execution dates, invocation counts, or individual task logs.
-   Apply the same user approval rules to additions, updates, and removals
    in the skill list as to development standards.
