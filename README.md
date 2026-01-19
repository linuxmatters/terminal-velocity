# Terminal Velocity

**The A to Z of Modern Unix**

A curated list of outstanding CLI and TUI applications for Linux and macOS terminals, companion to the [Linux Matters](https://linuxmatters.sh) podcast.

---

## What's This Then?

Your terminal deserves better than tools designed when disco was king.

This isn't a comprehensive catalogue of every command-line utility ever written. It's an opinionated selection of modern tools that genuinely improve how you work in the terminal. Think of it as recommendations from a friend who's tried the lot and picked out the gems.

Every tool here earns its place by being **bloody marvellous** at what it does, not just by existing. We focus on user experience: faster, friendlier, and more capable than whatever shipped with your distro in 1997.

### Connection to the Podcast

These recommendations accompany the "A to Z of Modern Unix" segment on [Linux Matters](https://linuxmatters.sh), where we meander through the alphabet when the mood takes us, showcasing the best of what the modern terminal has to offer.

### What Makes a Tool Modern?

Not everything with a Git repo gets in. We're after tools that deliver a noticeably superior experience over the crusty defaults: better UI, novel approaches to old problems, or performance improvements that make you wonder what the old tool was playing at. Ideally all three, but nail one brilliantly and you're in with a shout.

---

## The List

Entries are ordered alphabetically. Each tool includes what it replaces, why you'd want it, and tips to get you started.

<!-- Entries go here, alphabetically ordered -->

### [`ripgrep`](https://github.com/BurntSushi/ripgrep) (`rg`)

**Replaces:** `grep`, `ack`, `ag`

> Recursively searches directories for regex patterns, respecting your gitignore automatically.

**Why it's brilliant:** You'll stop typing `grep -r` forever. Point it at any codebase and it instantly knows what to skip: hidden files, binary blobs, everything in your `.gitignore`. The speed difference isn't subtle; it's the kind of fast that makes you search more freely because results appear before your finger leaves the Enter key.

**Killer feature:** Automatic `.gitignore` respect means you search only what matters, no configuration required.

<details>
<summary>Screenshot</summary>

![ripgrep searching a codebase with coloured output](https://burntsushi.net/stuff/ripgrep1.png)

</details>

**Pro tip:** Use `-tpy` or `-tjs` to instantly filter by language without remembering file extensions.

**Pairs well with:** [`fzf`](#fzf) for interactive filtering of search results.

<!-- Add new entries above this line, in alphabetical order -->

---

## Contributing

Spotted a brilliant tool we've missed? Contributions are welcome. But fair warning, Martin is a fussy so-and-so and will be a ruthless judge of your opinions. If you do suggest something cracking, you'll get a mention on the podcast.

- **One tool per PR** for new entries
- **Check it's actively maintained** (commits within the last 2 years)
- **Follow the entry format** in [CONTRIBUTING.md](CONTRIBUTING.md)
- **Place entries alphabetically** within the list

See the full guidelines in [CONTRIBUTING.md](CONTRIBUTING.md).

---

## Licence

This work is licensed under [Creative Commons Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/).

You're free to share and adapt this content, provided you give appropriate credit.
