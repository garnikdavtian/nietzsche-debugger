# nietzsche-debugger

A [Claude Code](https://claude.com/claude-code) skill that won't fix your bug. It asks you one question at a time until you find the cause yourself.

Based on [DilawarShafiq/nietzschian-debugger](https://github.com/DilawarShafiq/nietzschian-debugger), a Python CLI. This version is a single `SKILL.md`: Claude is the model, so there is nothing to install and no API key to set.

## Install

```bash
git clone https://github.com/garnikdavtian/nietzsche-debugger.git
cp -r nietzsche-debugger/nietzschian-debugger ~/.claude/skills/
```

## Usage

```
/nietzschian-debugger login returns 403, but only for users who signed up before last week
/nietzschian-debugger debug --diff tests started failing after my last change
/nietzschian-debugger debug --lens socrates my endpoint is slow
/nietzschian-debugger predict ./parsers.py -n 5
/nietzschian-debugger roast ./legacy/utils.py
/nietzschian-debugger share -o session.md
```

During a session, type `found it` when you have the cause, `I give up` for one last question, or `exit` to stop.

## Modes

- **debug**: one question per turn, never the answer. It switches between three styles depending on how you answer: socrates when you're vague, nietzsche when you're leaning on an assumption, zarathustra when you want to quit. It ends with a score for assumption-checking, evidence-gathering and root-cause speed.
- **predict**: picks a function in your file and asks what a specific call returns, then runs it to check. At the end it tells you what kind of code you tend to misread.
- **roast**: one or two lines about the worst thing in a file.
- **share**: prints the session as markdown.

## Differences from the original

- No model choice and no `demo` command: Claude runs it.
- Scores cover the current session only. The original also keeps a history across sessions.
- `predict` runs Python only.

## License

MIT. See [LICENSE](LICENSE).
