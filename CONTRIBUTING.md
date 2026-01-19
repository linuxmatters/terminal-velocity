# Contributing

Terminal Velocity is a curated _"awesome list"_ of outstanding CLI and TUI applications for Linux/Unix terminals; a companion to the "A to Z of Modern Unix" segment on [Linux Matters](https://linuxmatters.sh) podcast.

## Project overview

- **Type:** Curated content (Markdown README)
- **Licence:** CC-BY-4.0
- **Audience:** Technical users and developers on Linux and macOS
- **Tone:** Enthusiastic, opinionated British English - recommendations from a knowledgeable friend, not Wikipedia

## What qualifies as Modern?

A tool earns its place by excelling in at least one of these areas:

- **Superior UI/UX** - noticeably better interface than traditional equivalents
- **Novel approach** - solves the problem in a genuinely new way
- **Dramatically faster** - performance that makes the old tool look embarrassing

The best entries tick all three boxes, but exceptional execution of one is enough. We're not cataloguing every CLI utility ever written; we're picking the gems worth switching to.

## Content structure

Each tool entry follows this format:

```markdown
### [`tool-name`](https://github.com/user/repo) (`command`)

**Replaces:** `classic-tool`

**Featured in:** _(Optional)_ [Episode 42](https://linuxmatters.sh/42/)

> One-liner description (15 words max).

**Why it's brilliant:** 2-3 sentences, 50-75 words. Focus on user experience, not implementation.

**Killer feature:** One standout capability (25 words max).

<details>
<summary>Screenshot</summary>

![Description](url-to-image)

</details>

**Pro tip:** _(Optional)_ Non-obvious but useful feature (20 words max).

**Pairs well with:** _(Optional)_ [`other-tool`](#other-tool) for specific use case.
```

## Content guidelines

- Every entry is a five-star pick; no ratings needed
- Focus on "bloody marvellous" user experience, not implementation details
- Language/framework is not a feature (the Go/Rust joke is acknowledged but not catalogued)
- Use official project screenshots or GIFs where available
- Collapsible screenshots keep the list scannable
- Cross-platform appeal: Linux and macOS users welcome

## Word limits

| Field              | Limit                    |
| ------------------ | ------------------------ |
| One-liner          | 15 words                 |
| Why it's brilliant | 50-75 words              |
| Killer feature     | 25 words                 |
| Pro tip            | 20 words                 |
| Pairs well with    | 10 words after tool name |
| Featured in        | Episode link only        |

## Writing style

- British English spelling (colour, behaviour, organisation)
- Hyphens or commas, never emdashes
- Contractions welcome (it's, don't, you'll)
- Active voice, direct address
- No emoji in entry content

## PR guidelines

- One tool per PR for new entries
- Use Conventional Commits: `feat: add toolname entry`
- Verify all links resolve
- Use official project assets for screenshots
- Alphabetical placement within the list

## Constraints

- Do not add tools without a working public repository
- Do not include abandoned projects (no commits in 2+ years)
- Do not duplicate entries; update existing ones instead
- Do not exceed word limits - brevity is a feature
