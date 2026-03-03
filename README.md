# Symlink Tutorial

An interactive symlink crash course, powered by [Claude Code](https://docs.anthropic.com/en/docs/claude-code/overview). Learn by doing in ~55 minutes.

## How it works

The `CLAUDE.md` file primes Claude Code as a Socratic tutor. You open a session, it asks a couple of calibration questions, and then teaches you symlinks through hands-on exercises — you type every command, predict every result, and build your mental model from the ground up.

No lectures. No walls of text. Just a tight feedback loop: hypothesize, run, observe, discuss.

## Prerequisites

- [Claude Code](https://docs.anthropic.com/en/docs/claude-code/overview) installed
- A terminal running bash or zsh (macOS or Linux)
- ~55 minutes

## Quick start

```bash
git clone https://github.com/tommarshall/symlink-tutorial.git
cd symlink-tutorial
claude
```

That's it. The tutor takes over from there.

## What you'll learn

| Phase | Topic |
|-------|-------|
| 0 | Your existing mental model — surfaced and sharpened |
| 1-2 | Creating, inspecting, and editing through symlinks |
| 3 | Dangling symlinks — when targets disappear |
| 4 | Directory symlinks and the `pwd` paradox |
| 5 | **Relative vs absolute paths** — the crux of symlink mastery |
| 6 | Hard links vs soft links |
| 7 | Real-world patterns on your own machine |
| 8 | Common gotchas |
| 9 | Wrap-up — your mental model, refined |

## Pedagogical approach

The tutorial uses a Socratic method with structured hint escalation (inspired by CS50). The tutor:

- Asks you to **predict** before every command
- Lets **errors teach** — several exercises are designed to break things
- Uses **etymology** to make concepts stick ("Why is it called *symbolic*?")
- Adapts to your level — terminal beginners get more syntax help, power users get more autonomy
- Never explains what you can discover yourself

Progress is saved automatically, so you can take a break and pick up where you left off.

## Post-tutorial reference

After completing the tutorial, `symlinks-cheatsheet.md` serves as a quick reference for everything you learned.

## License

[MIT](LICENSE)
