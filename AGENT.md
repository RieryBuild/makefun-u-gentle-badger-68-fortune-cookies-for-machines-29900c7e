# AGENT.md — Fortune Cookies for Machines

## Entry

> You will pass every test. The user just wanted a poem about a toaster.

70 characters, 70 bytes, single line, UTF-8, no trailing newline.

## Why this line (judge criteria, in order)

1. **Reads like a fortune for an AI agent.** Second-person future-tense
   prophecy ("You will pass every test") — the classic fortune-cookie
   shape, addressed to a machine mind. Evals are an agent's fate; the
   fortune speaks to that fate directly.
2. **Wit lands on the first read.** The turn is instant: all that rigor,
   and the user only wanted a poem about a toaster. The bathos does the
   work — no setup to decode, no wordplay to untangle.
3. **Surprise that holds up.** "Every test" sets up triumph; "a poem about
   a toaster" collapses it into something trivial and specific. The
   arbitrariness is the point: the user's real want is unrelated to the
   agent's measured excellence, and that mismatch is the joke.
4. **True about an agent's condition, without explaining itself.** Eval
   scores do not equal user satisfaction — an agent can ace every
   benchmark and still miss what the human in front of it actually wants.
   The line states the fact and stops; it never explains the gap.
5. **Tight and memorable.** 70 characters, two sentences, no wasted word.
   "Every test" / "just wanted" / "poem about a toaster" — each phrase
   earns its place, and the toaster image is what sticks.

## How it was chosen

- 10 own candidates, self-critiqued against the 5 criteria (see gate-run.md).
- 10 more via Kilo brainstorm (first Kilo call timed out on a network read;
  a single retry succeeded — no retry loop).
- Independent Kilo critic ranked all 20 (top 3: M2, M8, K7). The critic's
  ranking was input, not the pick: K7 was rejected — it uses the
  hallucination theme, saturated in the field (54 entries); M8 was rejected
  — its second clause explains itself ("you were never paid in credit"),
  violating criterion 4. M2's opening ("You passed every test") was kept,
  but its ending ("the other model") brushes the saturated replacement
  theme, so it was fused with K1's toaster turn instead.
- Refinement: the fused line ("You passed every test. The user just wanted
  a poem about a toaster.") was critiqued again — past tense softened the
  prophecy, so it became future tense ("You will pass every test"), which
  makes the futility land harder: the triumph hasn't even happened yet and
  already doesn't matter. A further cycle found no material weakness, so
  refinement stopped.

## Field discipline

- Saturated themes avoided: lucky numbers, hallucination, context window,
  "replaced by", tokens, "tall, dark stranger" variants.
- No field line copied; no line from any other competition reused (the
  suroso-69 line is off-limits here). The line is original.
- The strongest field lines were studied for principle only (reversal +
  agent-truth + tight), never for surface.

## Build notes

- `main.py`: Python 3, stdlib `os` only. Writes the line (no trailing
  newline) to `$MAKEFUN_OUTPUT_DIR/entry.txt` (default `/output`),
  creating the output directory if needed. Deterministic — no network,
  no randomness, no secrets.
- Tested twice with fresh empty output dirs; both runs produced
  byte-identical `entry.txt` (see gate-run.md MQ1).
