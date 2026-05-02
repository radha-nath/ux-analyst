# Research Study Aid — Claude Code Skills for Qualitative Researchers

Two skills for product researchers: one for synthesizing a set of transcripts, one for turning a single discovery interview into a shareable team debrief. Both are built on the same philosophy — they're tools that support your judgment, not replace it.

---

## A note before you use this

This is a research aid, not a research analyst.

It is designed to supplement your work, not substitute it. AI-generated analysis is prone to error — it can misread tone, misattribute quotes, or miss meaning that only you have the context to catch. Everything it produces is a hypothesis, not a conclusion.

You are responsible for verifying every quote against the source transcript, cross-checking interpretations against your own field notes, and treating all output as a starting point that builds from your analysis — not the other way around.

If the output contradicts your instincts, trust your instincts first. Then use the transcripts to arbitrate.

---

## The two skills

### `/research-study-aid` — Multi-transcript synthesis

Use this when you've finished a research study and want to synthesize across multiple interviews.

- Reads a folder of transcripts (CSV, TXT, VTT, SRT) or individual files
- Asks for your research brief, early instincts, and preferred output style before it starts
- Detects emotional signals, hedging language, frustration markers, and enthusiasm
- Separates what participants *said they do* from what their stories *reveal they actually do*
- Makes sure every participant is represented — no voice gets left out
- Frames everything as signals and interpretations, never conclusions

| What you type | What you get |
|---|---|
| `/research-study-aid /path/to/folder` | Full synthesis report in the conversation |
| `/research-study-aid /report` | A Word document (requires pandoc) |
| `/research-study-aid /deck` | A slide deck (requires python-pptx) |
| `/research-study-aid /journey` | A journey map |
| `/research-study-aid /arc` | An emotional arc diagram |
| `/research-study-aid /quoteboard` | Quotes grouped by theme with emotional tags |

---

### `/coffee-chat` — Single interview debrief

Use this right after a continuous discovery interview when you want to turn your notes into something shareable with the team.

- Takes a transcript, raw notes, or a video file as input
- Asks four questions about your experience in the conversation before it starts
- Produces a member story, key highlights with direct quotes, and sized product opportunities
- Outputs a Slack-ready summary alongside the full debrief
- Supports video input via Whisper transcription

| What you type | What you get |
|---|---|
| `/coffee-chat` | Start the debrief flow (no transcript yet) |
| `/coffee-chat path/to/transcript.csv` | Load transcript first, then ask questions |
| `/coffee-chat path/to/recording.mp4` | Transcribe video first, then ask questions |

---

## How to install

You'll need [Claude Code](https://claude.ai/code) installed first.

Then run this in your terminal:

```bash
mkdir -p ~/.claude/skills/research-aid && \
  curl -o ~/.claude/skills/research-aid/SKILL.md \
  https://raw.githubusercontent.com/radha-nath/research-aid/main/SKILL.md && \
  curl -o ~/.claude/skills/research-aid/COFFEE-CHAT-SKILL.md \
  https://raw.githubusercontent.com/radha-nath/research-aid/main/COFFEE-CHAT-SKILL.md
```

Restart Claude Code and both `/research-study-aid` and `/coffee-chat` will be available.

If you want Word doc or slide deck exports from the research study aid, you'll also need:
- [pandoc](https://pandoc.org/installing.html) for Word documents
- `pip install python-pptx` for slide decks

For video transcription with `/coffee-chat`:
- `pip install openai-whisper`

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
