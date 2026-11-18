# autism-support-skill

**English** | [简体中文](README.zh-CN.md) | [日本語](README.ja.md)

Agent skill that helps families support an autistic child, adolescent, or adult in everyday life: communication, emotions, learning, sensory needs, daily living, and age-appropriate goals.

```bash
npx skills add sendsoon/autism-support-skill
```

This skill does **not** diagnose autism, prescribe treatment, or promise to remove autistic traits.

## What this skill does

`autism-support-skill` is a reusable workflow for coding agents (Cursor, Claude Code, Codex, and others that load `SKILL.md`). When a caregiver describes a real difficulty, the agent:

1. Separates what is known from what is still a hypothesis
2. Reads the situation across development, communication, emotion, sensory input, setting, and safety
3. Gives steps the family can try in that setting
4. States what to watch, what not to do, and when a qualified professional should assess

Eye contact, quiet compliance, and looking "typical" are not the success criteria.

## When to use it

Use this skill for practical questions about autism, ASD, AAC, distress, peers, attention, self-care, school inclusion, or the transition to adulthood.

Do not use it to decide whether someone is autistic, to recommend unproven cures, or to replace a clinician, therapist, or school team.

## Install

```bash
npx skills add sendsoon/autism-support-skill
```

Or clone the repository and copy `SKILL.md`, `references/`, and `examples/` into your agent's skills directory.

The [skills.sh](https://skills.sh/) catalog page updates after install telemetry arrives.

## Update the skill

If you installed with the Skills CLI, pull the latest `SKILL.md` from GitHub:

```bash
npx skills check
npx skills update autism-support-skill
```

`check` only reports whether a newer hash exists. `update` reinstalls this skill into the same agents as before. To refresh every installed skill:

```bash
npx skills update
```

Skip the confirm prompt with `-y`:

```bash
npx skills update autism-support-skill -y
```

Re-running the install command also refreshes the files:

```bash
npx skills add sendsoon/autism-support-skill
```

If you copied files by hand, `git pull` this repository and copy `SKILL.md`, `references/`, and `examples/` over the previous copy.

## Usage

```text
My 4-year-old pulls me to the cupboard when he wants a snack but does not say the name. What can we do at home?
He cries at every change of plan. How do I support him without forcing him through it?
How should I talk with school about support that fits him?
```

If a missing fact would change the suggestion, the agent should ask one question, not a long intake form.

## Output

```text
### 一、问题理解
### 二、可能原因分析
### 三、专业建议
### 四、具体实施步骤
### 五、注意事项
### 六、观察与评估
### 七、后续建议
```

Short questions can use a shorter form. A fictional filled example is in [examples/output-template.md](examples/output-template.md).

## Project layout

This repository is a **single-skill package**. The skill lives at the repo root so `npx skills` discovers it first.

```text
autism-support-skill/
├── SKILL.md                      # Agent entry: frontmatter + workflow
├── skills.sh.json                # skills.sh repo-page grouping
├── README.md                     # English
├── README.zh-CN.md               # Simplified Chinese
├── README.ja.md                  # Japanese
├── LICENSE
├── references/
│   ├── age-stages.md             # Age bands and focus areas
│   └── support-strategies.md     # Evidence-informed methods and limits
└── examples/
    └── output-template.md        # Response shape and a fictional example
```

| File | Role |
|---|---|
| `SKILL.md` | What the agent executes. YAML `name` / `description` control discovery. |
| `skills.sh.json` | Groups the skill under **Family support** on the skills.sh repo page. Does not change install behavior. |
| `README.md` / `README.zh-CN.md` / `README.ja.md` | Human-facing docs in three languages. |
| `references/` | Progressive disclosure. Read when choosing an age focus or a support method. |
| `examples/` | Output shape and a fictional example. |

## License

[MIT](LICENSE)
