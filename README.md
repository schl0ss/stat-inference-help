# Basic Statistical Inference — Claude Code Skill

A [Claude Code](https://claude.com/claude-code) skill for teaching basic statistical inference. Built from 13 years of original high school statistics teaching notes.

Type `/stathelp` in Claude Code to get help explaining concepts, walking through inference problems step-by-step, or developing teaching strategies using the 4C Method.

AP® is a registered trademark of the College Board, which was not involved in the production of, and does not endorse, this skill.

## What It Does

- Walks through inference problems using the **4C Method** (Choose, Check, Calculate, Conclude)
- Always starts conclusions with a **p-value interpretation**
- Includes **TI-84 calculator commands** for every inference procedure
- Flags **common student errors** specific to each problem type
- Covers a full introductory statistics curriculum (9 units)

## Files

| File | Description |
|------|-------------|
| `SKILL.md` | Main skill — response templates, core principles, formatting rules |
| `references/CURRICULUM.md` | Full curriculum map (Units 1–9), exam format, four-step framework |
| `references/INFERENCE.md` | Deep inference guide — 4C method, conditions tables, procedure selection flowchart, calculator commands, Type I/II errors, power, scope of inference |

## Installation

Copy the skill folder into your Claude Code skills directory:

```bash
# Clone this repo
git clone https://github.com/schl0ss/claude-skill-stathelp.git

# Copy to your Claude Code skills directory
cp -r claude-skill-stathelp ~/.claude/skills/stathelp
```

Then type `/stathelp` in any Claude Code session to activate it.

## Example

```
/stathelp Walk me through a two-proportion z-test for this problem:
In 2014, 19.7% of 61 randomly selected kochia plants were resistant
to glyphosate. In 2017, 38.5% of 52 randomly selected kochia plants
were resistant. Is there convincing evidence of an increase at α = 0.05?
```

The skill will respond with a full 4C walkthrough: procedure identification, conditions checked with numbers, test statistic and p-value with calculator command, and a conclusion starting with the p-value interpretation.

## Background

Built by a statistics teacher with 13 years of classroom experience. The teaching approach prioritizes conceptual understanding over procedural calculation: p-value interpretation as a teaching tool, simulation-based intuition before formal inference, and the specific vocabulary and frameworks that exam scoring rubrics reward.

## License

MIT
