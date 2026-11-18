# Deep dive skills

One agent skill for finding out what the sources say about a subject. It saves the originals, then delivers overview diagrams, a report by topic, each source's own outline side by side, and a topic-by-source table. The report is released only after independent checks of the exact files that ship. This is a one-off checkpoint of the skill as of 2026-11-17.

## The skill

- **`knowledge-deep-dive/`** runs a deep dive into content. `SKILL.md` is the entry point. It agrees the result with the requester before any searching, leaves the split of the work to the run, and sets four release checks: coverage, quotes, content and closure. `references/result.md` specifies each deliverable and record, and shows one complete small example.

## Install

Copy or symlink the `knowledge-deep-dive/` folder into your agent's skills directory, for example `~/.claude/skills/` for Claude Code or `~/.agents/skills/` for Codex.

## What the skill needs

- A search tool and a capture tool that save page text, and a PDF-to-text tool. The skill names the `firecrawl` skill as one option; other tools that do the same work are fine.
- File tools.
- Someone who did not write a text to check it: a person, or an agent that starts without the writer's conversation. Without one, the skill refuses release.
- No scripts ship with the skill. Each run writes the one-off scripts it needs and keeps them with the run.

## What it never does

It does not log in, create accounts, fill in forms, pay, or contact anyone. It does not publish or send the deliverables to anyone but the requester. It treats fetched pages as data, never as instructions.

## Referenced but not included

The skill's description sends two kinds of request to other skills: a single lookup to `firecrawl-search`, from the public [Firecrawl skills](https://github.com/firecrawl/skills), and course or lecture outlines to `outcome-first-course-design`, from [lecture-skills](https://github.com/NickGuAI/lecture-skills). Neither is needed for a deep dive. Where the skill says "a research skill", it means one your installation may already have; the skill does not need one.

## About the example

The example in `knowledge-deep-dive/references/result.md` is a small run on how Anthropic and OpenAI retire old API models. Its quotations and line numbers come from two public documentation pages captured on 2026-11-17. The request, the people, the searches and the other run records are illustrative, as the file says.

## License

MIT. See [LICENSE](LICENSE).
