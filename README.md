# Was It The Agent? 🕵️

> 100% vibe coded. No regrets.

Ever stare at a file and wonder *"did a human write this or did some robot do it while vibing to lo-fi beats?"* — this tool answers that question.

It runs `git blame` on any file and fingerprints every commit for signs of AI agents: co-author trailers, bot emails, generator footers. Then it tells you, line by line, who (or what) did the work.

---

## Install

**The clean way (recommended):**

```bash
pipx install was-it-the-agent
```

**Or plain pip:**

```bash
pip install was-it-the-agent
```

**Or straight from the repo:**

```bash
pip install git+https://github.com/syam000/Was-It-The-Agent.git
```

No dependencies. Just Python 3.8+ and git.

---

## Use it

```bash
wita path/to/some/file.py
```

```bash
wita README.md --summary          # just the ratio, skip the lines
wita app.js --only agent          # show me the robot parts
wita main.go --no-color           # for the minimalists
```

---

## What it detects

Claude Code · GitHub Copilot · Cursor · Codex · Devin · Aider · generic bots

Each line gets a verdict: `AGENT` · `HUMAN` · `MAYBE` — with a confidence level (high / medium / low).

---

## Sample output

```
  1 HUMAN  Human (-)           package main
  2 AGENT  Claude Code (high)  func suspiciouslyCleanFunction() {
  3 AGENT  Claude Code (high)      // perfectly formatted, zero typos
  4 HUMAN  Human (-)           }

── Was It The Agent? ──
  file:   main.go
  lines:  4
  agent:  2 (50%)
  human:  2
  by agent: Claude Code: 2

  verdict: still mostly human hands here.
```

---

*Built with vibes. Powered by `git blame`. Fueled by existential curiosity.*
