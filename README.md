# UX Research Analyst — A Claude Code Skill

A skill for qualitative researchers. Point it at a folder of interview transcripts and it helps you move faster — surfacing patterns, organizing quotes, and structuring a first draft of your narrative — without replacing your judgment as the person who was in the room.

---

## A note before you use this

This is a research aid, not a research analyst.

It is designed to supplement your work, not substitute it. AI-generated analysis is prone to error — it can misread tone, misattribute quotes, or miss meaning that only you have the context to catch. Everything it produces is a hypothesis, not a conclusion.

You are responsible for verifying every quote against the source transcript, cross-checking interpretations against your own field notes, and treating all output as a starting point that builds from your analysis — not the other way around.

If the output contradicts your instincts, trust your instincts first. Then use the transcripts to arbitrate.

---

## What it does

- Reads transcripts from a folder or individual files (CSV, TXT, plain notes, or subtitle files from recordings)
- Asks you for your research brief, early instincts, and preferred output style before it starts
- Detects emotional signals, hedging language, frustration markers, and enthusiasm in how participants spoke
- Separates what participants *said they do* from what their stories *reveal they actually do*
- Makes sure every participant is represented — no voice gets left out
- Frames everything as signals and interpretations, never conclusions — always with sample size acknowledged
- Follows your narrative lead; will flag when the data points elsewhere, but defers to your judgment

### What you can generate

| What you type | What you get |
|---|---|
| `/research-aid /path/to/folder` | Full synthesis report in the conversation |
| `/research-aid /report` | A Word document (requires pandoc) |
| `/research-aid /deck` | A slide deck (requires python-pptx) |
| `/research-aid /journey` | A journey map |
| `/research-aid /arc` | An emotional arc diagram |
| `/research-aid /quoteboard` | Quotes grouped by theme with emotional tags |

---

## How to install it

You'll need [Claude Code](https://claude.ai/code) installed first.

Then run this in your terminal:

```bash
mkdir -p ~/.claude/skills/research-aid && \
  curl -o ~/.claude/skills/research-aid/SKILL.md \
  https://raw.githubusercontent.com/radha-nath/ux-analyst/main/SKILL.md
```

Restart Claude Code and the `/research-aid` command will be available.

If you want Word doc or slide deck exports, you'll also need:
- [pandoc](https://pandoc.org/installing.html) for Word documents
- `pip install python-pptx` for slide decks

---

## How to use it

**Analyze a whole folder of transcripts:**
```
/research-aid /path/to/your/transcripts/
```
It will list the files it finds and ask you to confirm before starting.

**Analyze one file:**
```
/research-aid path/to/interview.csv
```

**At the start, it will ask you three things:**

1. What was the goal of this research? What questions were you trying to answer?
2. Do you have any early instincts or findings you want explored?
3. Do you want the output plain and direct, or more formal?

Your answers shape the whole analysis. The more specific you are, the more useful it gets.

---

## The philosophy behind it

This skill was built with a specific philosophy. If you modify it, these are worth preserving:

- **Researcher autonomy first.** The researcher was in the room. Their judgment overrides AI interpretation.
- **Epistemic honesty always.** Never state findings as facts. Always acknowledge sample size. Treat every insight as a hypothesis.
- **Evidence before interpretation.** Every claim needs a citation and a participant count. No exceptions.
- **Equal participant representation.** No voice should dominate the analysis at the expense of others.
- **Distinguish description from interpretation.** Be precise about what was observed. Be humble about what it means.

---

## Want to contribute or suggest changes?

This was built from real research practice and will keep getting better with input from people who use it. Good areas to push on: support for more transcript formats, non-English transcripts, richer visual outputs, and prompt refinements from actual field use.

Open an issue or reach out before making a big change — happy to think through it together.

---

## Using or sharing this

Free to use and modify by researchers. Credit appreciated.

Please preserve the design philosophy when adapting it. If you have ideas for how to evolve it — reach out: [@radha-nath](https://github.com/radha-nath)

---

*Built by Radha, product thinker, iterated with Claude Code.*
