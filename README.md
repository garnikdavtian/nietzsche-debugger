# nietzschian-debugger (Claude Code skill)

A Claude Code skill port of [DilawarShafiq/nietzschian-debugger](https://github.com/DilawarShafiq/nietzschian-debugger).
It never hands you the fix: it asks exactly one sharp question per turn until you find the root cause yourself.

Modes: `debug` (default, adaptive socrates / nietzsche / zarathustra lenses, `--lens`, `--diff`),
`predict <file>` (predict what your function returns, then it runs the code for the truth),
`roast <file>`, and `share`.

## Install

```bash
git clone git@github.com:garnikdavtian/nietzsche-debugger.git
cp -r nietzsche-debugger/nietzschian-debugger ~/.claude/skills/
```

## Use

```
/nietzschian-debugger My API returns 500 but only on Tuesdays
/nietzschian-debugger predict ./parsers.py -n 5
/nietzschian-debugger roast ./legacy/utils.py
```

In a session type `found it` / `solved` to finish, `I give up` for one lifeline question, `exit` to quit.
