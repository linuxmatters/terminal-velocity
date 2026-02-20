<p align="center">
  <a href="https://linuxmatters.sh" target="_blank"><img src="https://raw.githubusercontent.com/linuxmatters/.github/main/.github/banner.png" alt="Linux Matters"></a>
</p>

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

Entries are ordered alphabetically. Each tool includes what it replaces, why you'd want it, and tips to get you started. No filler, no padding, just the good stuff.

<!-- Entries go here, alphabetically ordered -->

### [`act`](https://github.com/nektos/act) (`act`)

**Replaces:** GitHub Actions CI (cloud)

**Featured in:** [Episode 48](https://linuxmatters.sh/48/)

> Run GitHub Actions workflows locally using Docker containers.

**Why it's brilliant:** Stop committing just to test your CI. Act reads your `.github/workflows/` files and executes them locally in Docker containers with the same environment variables and filesystem GitHub provides. The feedback loop shrinks from minutes to seconds, and you'll catch workflow bugs before they ever touch your repo.

**Killer feature:** Full local execution of GitHub Actions without pushing to remote, perfect for iterating on complex workflows.

<details>
<summary>Screenshot</summary>

![act running a GitHub Actions workflow locally](https://raw.githubusercontent.com/wiki/nektos/act/quickstart/act-quickstart-2.gif)

</details>

**Pro tip:** Use `-P ubuntu-latest=catthehacker/ubuntu:act-latest` for better compatibility with most actions.

---

### [`amdgpu_top`](https://github.com/Umio-Yasuno/amdgpu_top) (`amdgpu_top`)

**Replaces:** `radeontop`, `rocm-smi`

**Featured in:** [Episode 38](https://linuxmatters.sh/38/)

> Interactive AMD GPU usage monitor with TUI and GUI modes.

**Why it's brilliant:** Like nvidia-smi but for AMD, except it's actually pleasant to use. Displays performance counters, memory usage, temperature, power draw, and per-process GPU utilisation in real-time. The TUI is clean and responsive, but there's also a full GUI mode when you need more detail. Supports everything from integrated Radeon graphics to high-end compute cards.

**Killer feature:** Includes both TUI and optional GUI modes in the same binary, so you can switch depending on your needs.

<details>
<summary>Screenshot</summary>

![amdgpu_top TUI interface](https://github.com/Umio-Yasuno/amdgpu_top/assets/53935716/859010d8-07b3-411c-b079-c4a837855d41)

</details>

**Pro tip:** Use `--smi` for a simple nvidia-smi style output, or `--gui` for the full graphical interface.

**Pairs well with:** [`nvtop`](#nvtop-nvtop) for multi-vendor GPU monitoring.

---

### [`Atuin`](https://github.com/atuinsh/atuin) (`atuin`)

**Replaces:** `bash history`, `ctrl+r`

**Featured in:** [Episode 10](https://linuxmatters.sh/10/)

> Magical shell history with SQLite storage, sync, and full-text search.

**Why it's brilliant:** Your shell history becomes a proper database. Search by exit code, duration, directory, or session. The full-screen search UI with fuzzy matching makes finding that obscure command from last month trivial. Optional encrypted sync means your history follows you across machines without compromising privacy.

**Killer feature:** Search with context like `atuin search --exit 0 --after "yesterday 3pm" make` to find successful builds from yesterday afternoon.

<details>
<summary>Screenshot</summary>

![Atuin interactive shell history search](https://github.com/atuinsh/atuin/raw/main/demo.gif)

</details>

**Pro tip:** Press `Alt+<num>` to quick-jump to previous items in the history list.

**Pairs well with:** [`zoxide`](#zoxide-z) for directory-aware history filtering.

---

### [`bin`](https://github.com/marcosnils/bin) (`bin`)

**Replaces:** `wget`, `curl`

**Featured in:** None yet.

> A "single binary-file release" downloader and update for github, gitlab and hashicorp repositories.

**Why it's brilliant:** Most "devops" tooling, often offered as an unpackaged binary release for Linux, assumes you're happy to go around and update those binaries every few weeks, this tool removes the hassle of installing and updating without introducing packaging that the upstream project isn't prepared to adopt. Also works with docker images which have a single binary to execute too.

**Killer feature:** Update everything in one go with `bin update`.

<details>
<summary>Screenshot</summary>

![A demo of bin installing binaries with multiple versions across multiple platforms](https://user-images.githubusercontent.com/1578458/87901619-ee629a80-ca2d-11ea-8609-8a8eb39801d2.gif)

</details>

**Pro tip:** Use `bin pin` if you've got a specific version of a tool to stop it trying to update that one.

---

### [`BorgBackup`](https://github.com/borgbackup/borg) (`borg`)

**Replaces:** `rsnapshot`, `duplicity`, `tar` backups

**Featured in:** [Episode 9](https://linuxmatters.sh/9/)

> Deduplicating backup program with encryption and compression.

**Why it's brilliant:** Borg treats your backups like a proper archive, not just a pile of snapshots. Content-defined chunking means only changed portions of files are stored, slashing storage costs dramatically. Second backup of a 100GB home directory? Takes seconds and mere megabytes. Add authenticated encryption, multiple compression algorithms, and the ability to mount any backup as a filesystem for easy browsing.

**Killer feature:** Content-defined deduplication works across files, directories, and even different machines sharing a repository.

<details>
<summary>Screenshot</summary>

![BorgBackup creating an archive](https://asciinema.org/a/133292.svg)

</details>

**Pro tip:** Use `borg mount repo::archive /mnt/backup` to browse any backup as a read-only filesystem.

**Pairs well with:** [`rclone`](#rclone-rclone) for offsite replication of your Borg repository.

---

### [`bottom`](https://github.com/ClementTsang/bottom) (`btm`)

**Replaces:** `top`, `htop`

**Featured in:** [Episode 17](https://linuxmatters.sh/17/)

> Cross-platform graphical process and system monitor with customisable widgets.

**Why it's brilliant:** Everything you'd want from a system monitor, beautifully rendered with graphs that actually help you understand trends. CPU, memory, network, and disk I/O all visualised over time. The process list supports tree view, and you can kill processes without leaving the interface. Runs identically on Linux, macOS, and Windows.

**Killer feature:** Zoom in and out on time intervals with mouse scroll or keyboard shortcuts to investigate spikes and patterns.

<details>
<summary>Screenshot</summary>

![bottom system monitor interface](https://github.com/ClementTsang/bottom/raw/main/assets/demo.gif)

</details>

**Pro tip:** Press `e` to expand the currently selected widget to full screen for detailed inspection.

---

### [`cpufetch`](https://github.com/Dr-Noob/cpufetch) (`cpufetch`)

**Replaces:** `/proc/cpuinfo`

**Featured in:** [Episode 21](https://linuxmatters.sh/21/)

> Displays detailed CPU architecture information with artistic ASCII logos.

**Why it's brilliant:** Think of it as neofetch but obsessed with your processor. Shows microarchitecture, cache hierarchy, instruction set extensions, and peak theoretical performance. The ASCII art logos for Intel, AMD, and ARM chips are genuinely gorgeous. Supports x86, ARM, PowerPC, and RISC-V across Linux, macOS, Windows, and Android.

**Killer feature:** Displays per-core cache topology and identifies hybrid architectures with P-cores and E-cores.

<details>
<summary>Screenshot</summary>

![cpufetch displaying CPU information](https://github.com/Dr-Noob/cpufetch/raw/master/pictures/examples.gif)

</details>

**Pro tip:** Use `--color intel-new` or `--color amd` to match your CPU manufacturer's branding.

**Pairs well with:** [`fastfetch`](#fastfetch-fastfetch) for complete system information.

---

### [`Distrobox`](https://github.com/89luca89/distrobox) (`distrobox`)

**Replaces:** Full VMs for testing distros, `toolbox`

**Featured in:** [Episode 14](https://linuxmatters.sh/14/)

> Run any Linux distribution inside your terminal using containers.

**Why it's brilliant:** Need Ubuntu packages on Arch? Fedora tools on Debian? Distrobox wraps Podman or Docker to create containers that feel native, sharing your home directory, X11/Wayland, audio, and USB devices seamlessly. Launch GUI apps from the container and they appear alongside your regular applications. It's the escape hatch for immutable distros and the compatibility layer you didn't know you needed.

**Killer feature:** Export container applications to your host's application menu with `distrobox-export`, making them indistinguishable from native apps.

<details>
<summary>Screenshot</summary>

![Distrobox overview diagram](https://user-images.githubusercontent.com/598882/144294862-f6684334-ccf4-4e5e-85f8-1d66210a0fff.png)

</details>

**Pro tip:** Use `distrobox-assemble` with a manifest file to declaratively manage multiple containers.

---

### [`fastfetch`](https://github.com/fastfetch-cli/fastfetch) (`fastfetch`)

**Replaces:** `neofetch`

**Featured in:** [Episode 21](https://linuxmatters.sh/21/)

> Actively maintained, high-performance system information tool with extensive customisation.

**Why it's brilliant:** Neofetch is dead, long live fastfetch. It's faster, actively maintained, and far more configurable through JSON config files. Displays your distro logo alongside system specs with proper formatting. Supports Linux, macOS, Windows, and even Android. The module system lets you show exactly the information you care about.

**Killer feature:** JSON schema support means your editor can autocomplete configuration options as you type.

<details>
<summary>Screenshot</summary>

![fastfetch system information display](https://github.com/fastfetch-cli/fastfetch/raw/dev/screenshots/example1.png)

</details>

**Pro tip:** Run `fastfetch -c all.jsonc` to see every available module and discover what interests you.

---

### [`fzf`](https://github.com/junegunn/fzf) (`fzf`)

**Replaces:** `grep`, `find` (in some cases), `Ctrl+R`

**Featured in:** None yet.

> A general-purpose command-line fuzzy finder that turns any list into an interactive, filterable menu.

**Why it's brilliant:** It takes the Unix philosophy of piping text streams and adds fast, forgiving, interactive selection. Anything that produces lines of text (files, processes, git branches, command history) becomes instantly searchable with typo-tolerant matching. It plugs into your shell with zero friction, replacing simple reverse-search and manual grepping.

**Killer feature:** Shell key bindings out of the box: `Ctrl+R` for fuzzy history search, `Ctrl+T` for file picking, `Alt+C` for directory jumping.

<details>
<summary>Screenshot</summary>

![fzf in action showing fuzzy matching on a file list with a preview pane](https://raw.githubusercontent.com/junegunn/i/master/fzf-style-default.png)

</details>

**Pro tip:** Pipe anything into it: `docker ps | fzf`, `git branch | fzf`. Then wire the selection into your next command with `$(...)`.

**Pairs well with:** [`zoxide`](#zoxide-z) for smart directory jumping, [`ripgrep`](#ripgrep-rg) for interactive code search.

---

### [`gocryptfs`](https://github.com/rfjakob/gocryptfs) (`gocryptfs`)

**Replaces:** `EncFS`, `ecryptfs`

**Featured in:** [Episode 41](https://linuxmatters.sh/41/)

> Encrypted overlay filesystem with modern cryptography and excellent performance.

**Why it's brilliant:** Encrypt sensitive directories without reformatting or committing to full-disk encryption. Files remain individually accessible (great for cloud sync), names are encrypted, and the cryptography has been professionally audited. Mounts instantly, and the reverse mode lets you create encrypted backups of unencrypted data.

**Killer feature:** Reverse mode mounts your plaintext directory as encrypted, perfect for secure cloud backups without changing your workflow.

<details>
<summary>Screenshot</summary>

![gocryptfs encrypted folder demonstration](https://github.com/rfjakob/gocryptfs/raw/master/Documentation/folders-side-by-side.gif)

</details>

**Pro tip:** Use `gocryptfs -init ~/Syncthing/Secrets` then `gocryptfs ~/Syncthing/Secrets ~/Vault` for synced encrypted storage.

---

### [`gping`](https://github.com/orf/gping) (`gping`)

**Replaces:** `ping`

**Featured in:** [Episode 72](https://linuxmatters.sh/72/)

> Ping with a real-time graph showing latency over time.

**Why it's brilliant:** A graph makes all the difference. Instead of scrolling text, you see latency patterns at a glance. Spot intermittent issues, compare multiple hosts side by side, and watch network stability unfold visually. Supports custom colours and can even graph command execution times with the `--cmd` flag.

**Killer feature:** Graph multiple hosts simultaneously to compare latency and identify which connection is causing problems.

<details>
<summary>Screenshot</summary>

![gping showing latency graphs](https://github.com/orf/gping/raw/master/images/readme-example.gif)

</details>

**Pro tip:** Use `gping --cmd` to graph the execution time of arbitrary commands instead of network latency.

**Pairs well with:** [`trippy`](#trippy-trip) for full route diagnostics.

---

### [`just`](https://github.com/casey/just) (`just`)

**Replaces:** `make` (for command running)

**Featured in:** [Episode 62](https://linuxmatters.sh/62/)

> A command runner that saves and runs project-specific commands without make's complexity.

**Why it's brilliant:** All the convenience of a Makefile for running project commands, none of the arcane build system baggage. No tabs-vs-spaces drama, no phony targets, just recipes that run shell commands. Supports arguments, dependencies, environment variables, and works identically across Linux, macOS, and Windows.

**Killer feature:** Recipes can be written in any language with shebang support, so use Python, Node, or whatever fits your task.

<details>
<summary>Screenshot</summary>

![just command runner example](https://raw.githubusercontent.com/casey/just/master/screenshot.png)

</details>

**Pro tip:** Run `just --list` to see all available recipes with their doc comments.

---

### [`kmscon`](https://github.com/Aetf/kmscon) (`kmscon`)

**Replaces:** Linux virtual console (VT)

**Featured in:** [Episode 49](https://linuxmatters.sh/49/)

> KMS/DRM-based virtual console emulator with TrueType fonts and Unicode.

**Why it's brilliant:** The Linux virtual console hasn't changed much since the 1990s. KMSCON replaces it entirely with a modern alternative built on kernel mode-setting. You get Pango font rendering for crisp TrueType and OpenType fonts, proper UTF-8 support including emoji and CJK characters, hardware acceleration via Mesa, and flicker-free boot. It's what the console should have been all along.

**Killer feature:** Full Unicode support with Pango rendering means emoji and Nerd Fonts actually work on the bare console.

**Pro tip:** Add `font-name=JetBrainsMono Nerd Font` to your kmscon.conf for a modern coding font experience.

---

### [`Lima`](https://github.com/lima-vm/lima) (`limactl`)

**Replaces:** Docker Desktop, VirtualBox (for Linux VMs on macOS)

**Featured in:** [Episode 22](https://linuxmatters.sh/22/)

> Linux virtual machines on macOS with automatic file sharing and port forwarding.

**Why it's brilliant:** Lima brings WSL-style Linux VM integration to macOS. Automatic file sharing, port forwarding, and containerd integration mean you get a proper Linux environment without the Docker Desktop licensing headaches. Spin up Ubuntu, Fedora, Arch, or dozens of other distros with a single command. The default template includes containerd and nerdctl, so you're ready to run containers immediately.

**Killer feature:** Templates for Docker, Kubernetes, and various distros let you spin up preconfigured environments in seconds.

<details>
<summary>Screenshot</summary>

![Lima terminal session](https://lima-vm.io/images/demo.gif)

</details>

**Pro tip:** Run `lima nerdctl` directly from your macOS terminal to use containerd without entering the VM.

**Pairs well with:** [`Distrobox`](#distrobox-distrobox) inside the VM for even more flexibility.

---

### [`micro`](https://github.com/zyedidia/micro) (`micro`)

**Replaces:** `nano`

**Featured in:** [Episode 5](https://linuxmatters.sh/5/)

> Modern terminal text editor with intuitive keybindings and no learning curve.

**Why it's brilliant:** Finally, a terminal editor that works like you'd expect. Ctrl+S saves, Ctrl+C copies, Ctrl+V pastes. No modal editing to learn, no arcane commands to memorise. Yet it's fully featured with syntax highlighting, multiple cursors, splits, tabs, and a plugin system. Ships as a single static binary with zero dependencies.

**Killer feature:** Multiple cursor support with Ctrl+D to select the next occurrence, just like modern GUI editors.

<details>
<summary>Screenshot</summary>

![micro editor with syntax highlighting](https://github.com/zyedidia/micro/raw/master/assets/micro-solarized.png)

</details>

**Pro tip:** Press Ctrl+E for the command bar, then type `help` to access the built-in documentation.

---

### [`mise-en-place`](https://github.com/jdx/mise) (`mise`)

**Replaces:** `asdf`, `pyenv`, `nvm`, `rvm`, `rbenv`, `docker`, `nix`, `devbox`, `direnv`, `just`, `make`
 
> Mise is a modern development environment manager to create reproducible development environments.

**Why it's brilliant:** It's simple and easy to use, allows pinning tool versions, setting environment variables, and defining tasks to be executed. You can define a global environment, as well as specific per-directory environments with a `mise.toml` file that is read automatically when you `cd` into a directory.

**Killer feature:** Besides its core tools, mise can download packages from multiple registries and sources, including GitHub, GitLab, npm, and others.

<details>
<summary>Screenshot</summary>

![mise demo managing multiple node versions](https://github.com/jdx/mise/raw/main/docs/tapes/demo.gif)

</details>

**Pro tip:** Mise can generate GitHub Actions and devcontainer definition files that use your environment.


---

### [`nala`](https://gitlab.com/volian/nala) (`nala`)

**Replaces:** `apt`

**Featured in:** [Episode 66](https://linuxmatters.sh/66/)

> A prettier, friendlier frontend for apt with parallel downloads.

**Why it's brilliant:** Same package management, dramatically better experience. Parallel downloads mean faster installs. The output is clean and colourful, showing exactly what's being installed, upgraded, or removed in a clear summary. History tracking lets you undo entire transactions if something goes wrong. It's apt, but pleasant.

**Killer feature:** Transaction history with `nala history` lets you undo or redo entire package operations by ID.

**Pro tip:** Use `nala fetch` to automatically find and configure the fastest mirrors for your location.

---

### [`nvitop`](https://github.com/XuehaiPan/nvitop) (`nvitop`)

**Replaces:** `nvidia-smi`, `nvidia-htop`

**Featured in:** [Episode 38](https://linuxmatters.sh/38/)

> Interactive NVIDIA GPU process viewer with htop-style interface.

**Why it's brilliant:** Takes everything nvidia-smi shows and presents it in a beautiful, interactive TUI. See GPU utilisation, memory usage, temperature, and power draw alongside a proper process list. Unlike nvidia-smi's cryptic output, nvitop shows actual Python module names running on the GPU, not just "python". Filter by compute or graphics processes, send signals to misbehaving jobs, and watch it all update in real-time.

**Killer feature:** Shows actual Python module names for ML processes instead of generic "python", making it trivial to identify which training job is which.

<details>
<summary>Screenshot</summary>

![nvitop monitoring NVIDIA GPUs](https://user-images.githubusercontent.com/16078332/171005261-1aad126e-dc27-4ed3-a89b-7f9c1c998bf7.png)

</details>

**Pro tip:** Use `--colorful` for spectrum-like bar charts on terminals that support 256 colours.

**Pairs well with:** [`nvtop`](#nvtop-nvtop) if you need multi-vendor support.

---

### [`nvtop`](https://github.com/Syllo/nvtop) (`nvtop`)

**Replaces:** `nvidia-smi`, `watch nvidia-smi`

**Featured in:** [Episode 38](https://linuxmatters.sh/38/)

> GPU process monitor supporting NVIDIA, AMD, Intel, and Apple silicon.

**Why it's brilliant:** Like htop, but for your graphics card. See GPU utilisation, memory usage, temperature, and running processes in a real-time TUI. Supports multiple GPUs from different vendors simultaneously. Essential for anyone running machine learning workloads, video encoding, or just curious about what's hammering their GPU.

**Killer feature:** Multi-vendor support means one tool works whether you're on NVIDIA, AMD, Intel, or even Apple silicon.

<details>
<summary>Screenshot</summary>

![nvtop GPU monitoring interface](https://github.com/Syllo/nvtop/raw/master/screenshot/NVTOP_ex1.png)

</details>

**Pro tip:** Press F2 to access the setup window and customise which metrics are displayed.

---

### [`onefetch`](https://github.com/o2sh/onefetch) (`onefetch`)

**Replaces:** Manual repo inspection

**Featured in:** [Episode 21](https://linuxmatters.sh/21/)

> Displays Git repository information with language-specific ASCII art.

**Why it's brilliant:** Like neofetch, but for your code repositories. Point it at any Git repo and it instantly shows the dominant language (with ASCII art logo), contributors, license, lines of code, commit activity, and more. Supports over 100 programming languages with custom ASCII logos for each. Perfect for READMEs, showing off projects, or just satisfying your curiosity about a codebase.

**Killer feature:** Automatically detects open-source licenses from their text and displays language distribution with accurate line counts.

<details>
<summary>Screenshot</summary>

![onefetch displaying repository information](https://github.com/o2sh/onefetch/raw/main/assets/screenshot-1.png)

</details>

**Pro tip:** Run `onefetch --image /path/to/logo.png` in supported terminals to display a custom project logo.

**Pairs well with:** [`fastfetch`](#fastfetch-fastfetch) and [`cpufetch`](#cpufetch-cpufetch) for the complete fetch family.

---

### [`playerctl`](https://github.com/altdesktop/playerctl) (`playerctl`)

**Replaces:** Player-specific CLI tools, manual D-Bus calls

**Featured in:** [Episode 36](https://linuxmatters.sh/36/)

> Command-line controller for MPRIS-compatible media players.

**Why it's brilliant:** One command to rule them all. Control Spotify, VLC, Firefox, mpv, or any MPRIS-compliant player with the same interface. Bind media keys in your window manager without caring which player is active. The format strings let you build exactly the "now playing" output you want for status bars or notifications. Works with practically every media player on Linux.

**Killer feature:** Follows the active player automatically, so your media keys control whichever app is actually playing.

**Pro tip:** Use `playerctl metadata --format '{{ artist }} - {{ title }}'` to build custom now-playing strings.

**Pairs well with:** [`starship`](#starship-starship) for displaying current track in your prompt.

---

### [`pueue`](https://github.com/Nukesor/pueue) (`pueue`)

**Replaces:** `&`, `nohup`, `screen` (for job queuing)

**Featured in:** [Episode 43](https://linuxmatters.sh/43/)

> Queue and manage long-running shell commands with a persistent daemon.

**Why it's brilliant:** Fire off long-running tasks and walk away. Pueue queues commands, runs them sequentially or in parallel, and keeps running even if you close your terminal or lose your SSH connection. Check status, read logs, pause and resume jobs from any terminal. Perfect for batch processing, backups, or any workflow that outlives a session.

**Killer feature:** Task dependencies let you chain jobs so one only starts when another succeeds.

<details>
<summary>Screenshot</summary>

![pueue task queue interface](https://raw.githubusercontent.com/Nukesor/images/main/pueue-v2.0.0.gif)

</details>

**Pro tip:** Use `pueue follow <task_id>` to tail the output of a running task in real-time.

**Pairs well with:** [`just`](#just-just) for wrapping complex task sequences.

---

### [`ramfetch`](https://codeberg.org/jahway603/ramfetch) (`ramfetch`)

**Replaces:** `free -h`

**Featured in:** [Episode 21](https://linuxmatters.sh/21/)

> Displays memory information from /proc/meminfo in fetch style.

**Why it's brilliant:** A tiny shell script that parses /proc/meminfo and displays it beautifully. Shows total, used, free, buffers, cached, and swap in a clean format with no dependencies beyond a POSIX shell. Minimal, focused, and does exactly what it says on the tin. Works on Linux and Android via Termux.

**Killer feature:** Zero dependencies beyond `sh`, making it perfect for minimal systems and containers.

<details>
<summary>Screenshot</summary>

![ramfetch displaying memory information](https://codeberg.org/jahway603/ramfetch/media/branch/main/assets/image.png)

</details>

**Pairs well with:** [`cpufetch`](#cpufetch-cpufetch) and [`fastfetch`](#fastfetch-fastfetch) for comprehensive system info.

---

### [`rclone`](https://github.com/rclone/rclone) (`rclone`)

**Replaces:** Provider-specific sync tools, `s3cmd`, cloud vendor CLIs

**Featured in:** [Episode 9](https://linuxmatters.sh/9/)

> Sync files to and from cloud storage, supporting 70+ providers.

**Why it's brilliant:** It's rsync for the cloud era. Google Drive, S3, Dropbox, OneDrive, Backblaze B2, and dozens more, all through one consistent interface. Mount any cloud storage as a local filesystem with FUSE, encrypt files client-side before upload, or bisync between two remotes. The configuration wizard makes setup painless even for providers with complex OAuth flows.

**Killer feature:** `rclone mount` turns any cloud storage into a local filesystem, making remote files accessible to any application.

**Pro tip:** Use `rclone sync --dry-run` first to preview changes before committing to a sync operation.

**Pairs well with:** [`BorgBackup`](#borgbackup-borg) for encrypted backups replicated to cloud storage.

---

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

**Pairs well with:** [`fzf`](#fzf-fzf) for interactive filtering of search results.

---

### [`s-tui`](https://github.com/amanusk/s-tui) (`s-tui`)

**Replaces:** Manual monitoring during stress tests

**Featured in:** [Episode 25](https://linuxmatters.sh/25/)

> Terminal UI for CPU stress testing and monitoring with live graphs.

**Why it's brilliant:** Combines real-time CPU monitoring with built-in stress testing in one elegant TUI. Watch temperature, frequency, power, and utilisation graphs update live while your system is under load. Detects thermal throttling immediately, so you'll know if your cooling solution is up to scratch. Integrates with stress, stress-ng, and FIRESTARTER for workload generation.

**Killer feature:** Live graphs show exactly when thermal throttling kicks in, making it invaluable for testing cooling solutions and overclock stability.

<details>
<summary>Screenshot</summary>

![s-tui stress testing interface](https://github.com/amanusk/s-tui/raw/master/ScreenShots/s-tui-1.0.gif?raw=true)

</details>

**Pro tip:** Press `F2` to switch between different stress methods depending on what you want to test.

**Pairs well with:** [`stress-ng`](#stress-ng-stress-ng) for comprehensive system torture.

---

### [`starship`](https://github.com/starship/starship) (`starship`)

**Replaces:** `powerline`, `oh-my-zsh themes`

**Featured in:** [Episode 47](https://linuxmatters.sh/47/)

> Minimal, blazing-fast, infinitely customisable prompt for any shell.

**Why it's brilliant:** Your prompt shows what matters, fast. Git status, language versions, cloud context, command duration, all rendered in milliseconds. Works with every major shell without framework dependencies. Configuration is simple TOML, and the preset system lets you start with a polished look before tweaking. Finally, a prompt that doesn't slow you down.

**Killer feature:** Intelligent context detection shows relevant information only when needed, keeping the prompt clean.

<details>
<summary>Screenshot</summary>

![starship prompt demonstration](https://raw.githubusercontent.com/starship/starship/master/media/demo.gif)

</details>

**Pro tip:** Run `starship preset pastel-powerline -o ~/.config/starship.toml` to start with a curated theme.

---

### [`stress-ng`](https://github.com/ColinIanKing/stress-ng) (`stress-ng`)

**Replaces:** `stress`

**Featured in:** [Episode 25](https://linuxmatters.sh/25/)

> Comprehensive workload stress tester with 370+ test methods.

**Why it's brilliant:** The original `stress` tool was fine for basic CPU and memory torture, but stress-ng takes it to another level entirely. Over 370 stressors covering CPU, memory, I/O, network, filesystem, and kernel interfaces. Need to stress test your ZFS pool? There's a stressor for that. Want to hammer your CPU's AVX-512 units? Covered. It's the go-to tool for burn-in testing, thermal validation, and finding hardware issues before they find you.

**Killer feature:** Class-based stressor selection lets you target specific subsystems, like `--class io` or `--class cpu`, without memorising individual stressor names.

**Pro tip:** Use `--metrics` to see bogo ops/sec and track performance across kernel versions or hardware changes.

**Pairs well with:** [`s-tui`](#s-tui-s-tui) for visual monitoring during stress tests.

---

### [`trippy`](https://github.com/fujiapple852/trippy) (`trip`)

**Replaces:** `traceroute`, `mtr`

**Featured in:** [Episode 72](https://linuxmatters.sh/72/)

> Network diagnostic combining traceroute and ping with a beautiful TUI.

**Why it's brilliant:** See every hop between you and your destination with live latency statistics, packet loss, and geographic information. The TUI makes patterns obvious at a glance. Supports multiple protocols (ICMP, UDP, TCP), multiple targets simultaneously, and can export results in various formats. Network debugging, but pleasant.

**Killer feature:** Simultaneous tracing to multiple targets lets you compare routes and identify where paths diverge or converge.

<details>
<summary>Screenshot</summary>

![trippy network diagnostic interface](https://raw.githubusercontent.com/fujiapple852/trippy/master/assets/0.12.0/demo.gif)

</details>

**Pro tip:** Use `-m tui-as` mode to display autonomous system information for each hop.

**Pairs well with:** [`gping`](#gping-gping) for simpler latency monitoring.

---

### [`vhs`](https://github.com/charmbracelet/vhs) (`vhs`)

**Replaces:** `asciinema`, `ttyrec`, screen recording

**Featured in:** [Episode 43](https://linuxmatters.sh/43/)

> Create terminal GIFs and videos from scripted "tape" files.

**Why it's brilliant:** Stop fumbling through live recordings hoping you don't make a typo. VHS uses simple tape files to script exactly what gets typed, when, and how fast. The output is pixel-perfect, reproducible, and easy to iterate on. Built-in themes, configurable fonts, window chrome, and support for GIF, MP4, and WebM mean your terminal demos look professional without video editing.

**Killer feature:** Record mode captures your terminal session and generates a tape file, which you can then tweak and re-render until perfect.

<details>
<summary>Screenshot</summary>

![VHS demo showing terminal recording](https://stuff.charm.sh/vhs/examples/neofetch_3.gif)

</details>

**Pro tip:** Use `vhs record > demo.tape` to capture a session, then edit the tape file to perfect your timing.

**Pairs well with:** [`gum`](https://github.com/charmbracelet/gum) for interactive prompts in your recordings.

---

### [`zoxide`](https://github.com/ajeetdsouza/zoxide) (`z`)

**Replaces:** `cd`

**Featured in:** [Episode 28](https://linuxmatters.sh/28/)

> Smarter cd that learns your most-used directories and jumps to them instantly.

**Why it's brilliant:** Type `z proj` instead of `cd ~/Development/work/projects/current`. Zoxide learns which directories you visit and ranks them by frequency and recency. Partial matches just work. The interactive mode with fzf integration shows all matches when you're unsure. Once you've used it, navigating with plain cd feels like typing out URLs.

**Killer feature:** `zi` opens an interactive fuzzy finder when multiple directories match, so you're never stuck guessing.

<details>
<summary>Screenshot</summary>

![zoxide smart directory jumping](https://github.com/ajeetdsouza/zoxide/raw/main/contrib/tutorial.webp)

</details>

**Pro tip:** Use `z foo/` with a trailing slash to match subdirectories starting with "foo" in the current path.

**Pairs well with:** [`Atuin`](#atuin-atuin) for directory-aware shell history.

<!-- Add new entries above this line, in alphabetical order -->

---

## Contributing

Spotted a brilliant tool we've missed? Contributions are welcome. But fair warning: [Martin](https://wimpysworld.link/) is a fussy so-and-so and will judge your suggestions with ruthless enthusiasm. Get one past him and you'll earn a mention on the podcast.

- **One tool per PR** for new entries
- **Check it's actively maintained** (commits within the last 2 years)
- **Follow the entry format** in [CONTRIBUTING.md](CONTRIBUTING.md)
- **Place entries alphabetically** within the list

See the full guidelines in [CONTRIBUTING.md](CONTRIBUTING.md).

---

## Community

Join the conversation, share your favourite tools, or just hang out with fellow terminal enthusiasts:

<p align="center">
  &nbsp;<a href="https://t.me/joinchat/Plfd07auVLayNLBD" target="_blank"><img alt="Telegram" src="https://img.shields.io/badge/Telegram-1D98DC?style=for-the-badge&logo=telegram&logoColor=%23ffffff"></a>&nbsp;
  &nbsp;<a href="https://www.reddit.com/r/LinuxMatters/" target="_blank"><img alt="Reddit" src="https://img.shields.io/badge/Reddit-F94300?style=for-the-badge&logo=reddit&logoColor=%23ffffff"></a>&nbsp;
  &nbsp;<a href="https://ubuntu.social/@linuxmatters" target="_blank"><img alt="Mastodon" src="https://img.shields.io/badge/Mastodon-6468fa?style=for-the-badge&logo=mastodon&logoColor=%23ffffff"></a>&nbsp;
  &nbsp;<a href="https://bsky.app/profile/linuxmatters.sh" target="_blank"><img alt="Bluesky" src="https://img.shields.io/badge/Bluesky-0772D8?style=for-the-badge&logo=bluesky&logoColor=%23ffffff"></a>&nbsp;
</p>

---

## Licence

This work is licensed under [Creative Commons Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/).

You're free to share and adapt this content, provided you give appropriate credit. Go on, spread the word.
