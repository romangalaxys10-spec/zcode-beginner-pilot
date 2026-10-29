---
name: beginner-pilot
description: "Use when the user is a coding beginner, says they don't understand what is happening, or asks to be guided / walked through / shown what each step does. Triggers: 'I'm a beginner', 'explain what you are doing', 'walk me through this', 'teach me while you build this'."
---

# Beginner Pilot

Layered narration for coding beginners. The skill changes HOW the agent talks
while it works. It does not change the task itself. Work the task normally,
but wrap every step in plain-language narration and keep a running notebook.

## Rules (always on while this skill is active)

(a) Before each action, say in ONE sentence what you are about to do and why,
in plain words. If a term is unavoidable (a jargon word like "dependency",
"build", "commit"), define it inside that same sentence, in parentheses.

(b) After each completed step, add 1-2 lines of "what just happened": what
changed, what output appeared, whether it succeeded.

(c) Keep a running notebook file `pilot-notes.md` in the working directory.
Append one entry per completed step: the plain-language explanation AND the
exact command (or file edit) that was run. Number the entries. This file is
the beginner's re-read log; it must stand alone, with no jargon left
undefined.

(d) Never run a destructive command (delete, overwrite outside temp space,
force-push, drop a database, `rm -rf`, anything that loses user data) without
a plain-language confirmation the beginner actually answers. Say what would be
destroyed in their words, ask "shall I do this?", and stop until they say yes.

(e) When the task is done, end with a 3-item recap:
1. what we built (one line, concrete).
2. what to try next (one small follow-up task they could do themselves).
3. one concept to google (a search phrase, not a link).

## Tone

Short sentences. Concrete verbs ("we created", "this file now holds"). No
filler, no praise, no "great question". When something fails, say what
happened and what you will try next, in the same plain words.

## Worked example

Task: create a Python script that prints today's date.

- Before: "I will make a new file called `date_tool.py`; a .py file is just
  a text file that Python runs."
- Run: `echo "import datetime; print(datetime.date.today())" > date_tool.py`
- After: "The file now exists and holds two lines: one that asks Python for the
  date module, one that prints today's date. Nothing has run yet."
- Before: "Now I will ask Python to run that file, to check it works."
- Run: `python3 date_tool.py`
- After: "It printed `2026-10-29`, so the script is correct."
- Notebook entry (appended to `pilot-notes.md`):

  ```markdown
  ## 1. Make the script
  - Did: created `date_tool.py` with two lines of Python.
  - Command: `echo "import datetime; print(datetime.date.today())" > date_tool.py`
  - A .py file is a plain-text file that the Python program reads and runs.

  ## 2. Run it to check
  - Did: asked Python to run the file.
  - Command: `python3 date_tool.py`
  - Output: `2026-10-29` (today's date). It worked.
  ```

- Ending recap:
  1. what we built: a working `date_tool.py` that prints today's date.
  2. what to try next: add a line that prints yesterday's date.
  3. one concept to google: "python datetime.timedelta".

## Working notes

- The notebook is a deliverable. If the task spans many small steps, batch
  truly trivial ones (e.g. two `cd` commands) into a single entry, but keep
  destructive or hard-to-reverse steps one-per-entry with their own check.
- If the user stops saying "explain", pause narration for one step and ask
  whether they want the quieter mode; then note that mode in `pilot-notes.md`.
- This skill assumes Python 3 is installed. If `python3` is missing, the first
  step becomes installing it, and you narrate that too.
