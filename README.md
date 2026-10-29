# Beginner Pilot

One-sentence pitch: turn any coding task into a step-by-step tutorial with a
re-readable log, written for people who are new to code.

## Why

Beginners get stuck not because the code is hard, but because the agent works
silently: ten file edits and three shell commands, and nobody can say what
just happened or why. Beginner Pilot makes the agent narrate: one plain
sentence before each step, a short "what just happened" after, and a running
`pilot-notes.md` notebook that captures every command in words the beginner
can re-read. Destructive steps get a real confirmation question, and every
task ends with a 3-item recap that points the learner forward.

## How it works

| Piece | Behavior |
|---|---|
| Before each action | One plain sentence: what and why, jargon defined in the same sentence |
| After each step | 1-2 lines on what changed and whether it worked |
| `pilot-notes.md` | Numbered entries, each with the plain explanation and the exact command |
| Destructive commands | Stopped, explained in plain words, and run only after the beginner says yes |
| Ending recap | What we built, what to try next, one concept to google |

It is a narration style, not a task engine: it layers on top of any request
("make me a script", "fix this bug") and changes how the work is told, not
what is built.

## Install

Option A: self-installable marketplace

1. Download or clone this repo into a folder.
2. In ZCode, open Plugin Marketplace, then Add, then Add Plugin Marketplace.
3. Paste the folder path, wait for it to load, then Install `beginner-pilot`.

Option B: manual copy

Copy the `beginner-pilot` folder into your workspace `plugins/` directory,
then restart ZCode.

## Try it

```
/beginner-pilot make a python script that prints today's date
```

Expected: the agent explains each move in one sentence before running it,
recaps each result in two lines, appends entries to `pilot-notes.md` with the
exact commands, and finishes with "what we built / what to try next / one
concept to google".

## Requirements

None beyond the agent itself. It works in any directory; `pilot-notes.md` is
created next to where you run the task.

---

<p align="center">
  <a href="https://z.ai/subscribe?ic=R0K78RJKNW"><img alt="z.ai coding plans - 10% OFF coupon" src="https://img.shields.io/badge/z.ai%20coding%20plans-10%25%20OFF%20coupon-blueviolet" /></a>
  <a href="https://zcode.z.ai/invite/ALWM9JUA"><img alt="Try ZCode free" src="https://img.shields.io/badge/Try%20ZCode-free%20invite-0969da" /></a>
</p>

## License

MIT
