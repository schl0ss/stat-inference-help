# AP Statistics — Claude Code Skill

A [Claude Code](https://claude.com/claude-code) skill for AP Statistics teaching. Built from 13 years of original teaching notes.

Type `/apstats` in Claude Code to get help explaining concepts, walking through inference problems step-by-step, or developing teaching strategies — all aligned with the College Board CED and AP exam scoring rubrics.

## What It Does

- Walks through inference problems using the **4C Method** (Choose, Check, Calculate, Conclude)
- Always starts conclusions with a **p-value interpretation**
- Includes **TI-84 calculator commands** for every inference procedure
- Flags **common student errors** specific to each problem type
- Covers all 9 units of the AP Statistics curriculum

## Files

| File | Description |
|------|-------------|
| `SKILL.md` | Main skill — response templates, core principles, formatting rules |
| `references/CURRICULUM.md` | Full AP Stats curriculum map (Units 1–9), exam format, four-step framework |
| `references/INFERENCE.md` | Deep inference guide — 4C method, conditions tables, procedure selection flowchart, calculator commands, Type I/II errors, power, scope of inference |

## Installation

Copy the `apstats` folder into your Claude Code skills directory:

```bash
# Clone this repo
git clone https://github.com/schl0ss/claude-skill-apstats.git

# Copy to your Claude Code skills directory
cp -r claude-skill-apstats ~/.claude/skills/apstats
```

Then type `/apstats` in any Claude Code session to activate it.

## Example

```
/apstats Walk me through a two-proportion z-test for this problem:
In 2014, 19.7% of 61 randomly selected kochia plants were resistant
to glyphosate. In 2017, 38.5% of 52 randomly selected kochia plants
were resistant. Is there convincing evidence of an increase at α = 0.05?
```

The skill will respond with a full 4C walkthrough: procedure identification, conditions checked with numbers, test statistic and p-value with calculator command, and a conclusion starting with the p-value interpretation.

## Background

Built by an AP Statistics teacher with 13 years of classroom experience. The teaching approach prioritizes conceptual understanding over procedural calculation — p-value interpretation as a teaching tool, simulation-based intuition before formal inference, and the specific vocabulary and frameworks the AP exam rewards.

## License

MIT
