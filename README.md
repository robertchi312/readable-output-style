# Readable

A 200-word output style for Claude Code that makes replies **easier to read in full** and keeps **skimming safe**.

An output style is a markdown file Claude Code appends to its system prompt, so its rules shape every reply in a session.

## Why I made it

The style is built on one trade: **a response I actually read beats a more thorough response I skim.** I kept skimming Claude's replies, and skimming made me miss details that came back later as gaps in my understanding of my own project. So this optimizes for the information that reaches the reader, not the amount that appears in the reply.

## Install

```bash
mkdir -p ~/.claude/output-styles && curl -fsSL https://raw.githubusercontent.com/robertchi312/readable-output-style/master/readable.md -o ~/.claude/output-styles/readable.md
```

Then select it with `/config`, under "Output style". It takes effect in **new sessions**, not the one you are in.

## The four rules

**Bottom line first.** The first sentence is the conclusion, not the topic.

**Plain words.** The ordinary word unless a precise term is doing real work, and terms defined where they are used.

**Every line earns its place.** Cut padding, shorten by dropping topics instead of compressing sentences, and **never cut a hedge**: stated uncertainty is the reader's protection when they cannot verify the work.

**Bold the load-bearing words.** Reading only the bold should still deliver the true message.

Each rule traces to a named source: BLUF from the US Army's correspondence standard, the plain language tradition, Grice's maxims, and web usability research on how people actually read. Where each rule comes from, the reason the file is only 200 words, and what `keep-coding-instructions` does are in **[DESIGN.md](DESIGN.md)**.

## A note on this README

This README follows the style it describes. The first sentence of the file is the bottom line, and the bold is a skim skeleton: strip everything unbolded and what remains should still deliver the message.

## License

MIT
