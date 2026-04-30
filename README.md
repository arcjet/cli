<a href="https://arcjet.com" target="_arcjet-home">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://arcjet.com/logo/arcjet-dark-lockup-voyage-horizontal.svg">
    <img src="https://arcjet.com/logo/arcjet-light-lockup-voyage-horizontal.svg" alt="Arcjet Logo" height="128" width="auto">
  </picture>
</a>

# Arcjet CLI

<p>
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://img.shields.io/github/v/release/arcjet/cli?style=flat-square&label=%E2%9C%A6Aj&labelColor=000000&color=5C5866">
    <img alt="GitHub release badge" src="https://img.shields.io/github/v/release/arcjet/cli?style=flat-square&label=%E2%9C%A6Aj&labelColor=ECE6F0&color=ECE6F0">
  </picture>
</p>

[Arcjet](https://arcjet.com) is the runtime security platform that ships with
your code. The Arcjet CLI gives you terminal access to the Arcjet security
platform — manage your sites, inspect traffic, and configure security rules
directly from the command line or through AI coding agents.

See the [Arcjet docs](https://docs.arcjet.com) for the full platform
documentation.

## Installation

### npx (recommended, no install)

Run the CLI directly without installing it. Works on macOS, Linux, and Windows:

```bash
npx -y @arcjet/cli@latest
```

### Homebrew (macOS and Linux)

```bash
brew install arcjet/tap/arcjet
```

### Install script (macOS and Linux)

```bash
curl -sSfL https://arcjet.com/cli/install.sh | bash
```

### Download a release

Download the latest binary for your platform from
[Releases](https://github.com/arcjet/cli/releases). Extract the archive and
place the `arcjet` binary somewhere on your `PATH`. This is primarily intended
for internal redistribution and air-gapped environments.

Available for macOS (Apple Silicon, Intel), Linux (x86_64, arm64), and Windows
(x86_64, arm64).

### Verify

```bash
arcjet version
```

## Authentication

Log in via your browser:

```bash
arcjet auth login
```

This opens a URL and displays a one-time code. Confirm the code in your browser
to complete login.

Check your authentication status:

```bash
arcjet auth status
```

Log out:

```bash
arcjet auth logout
```

For non-interactive use (CI, scripts, agents), set the `ARCJET_TOKEN`
environment variable instead of logging in interactively.

## Usage

```bash
# List your teams
arcjet teams list

# List sites for a team
arcjet sites list --team-id team_01abc123

# Get the SDK key for a site
arcjet sites get-key --site-id site_01abc123

# Get a security briefing
arcjet briefing --site-id site_01abc123

# Watch live requests
arcjet watch --site-id site_01abc123
```

Use `--output json` for machine-readable output. When stdout is not a TTY, JSON
is the default. Use `--fields` to limit output to specific keys.

Run `arcjet --help` to see all available commands, or
`arcjet <command> --help` for details on a specific command.

## Shell completions

Generate completion scripts for your shell:

```bash
# bash (current session)
source <(arcjet completion bash)
# bash (persist)
arcjet completion bash > /etc/bash_completion.d/arcjet

# zsh
arcjet completion zsh > "${fpath[1]}/_arcjet"

# fish (current session)
arcjet completion fish | source
# fish (persist)
arcjet completion fish > ~/.config/fish/completions/arcjet.fish
```

## Agent skills

Arcjet's agent-facing skills live at
[arcjet/skills](https://github.com/arcjet/skills) and are installed via the
[agentskills.io](https://agentskills.io) `skills` CLI into any compatible
client (Claude Code, Cursor, VS Code Copilot, and others):

```bash
npx skills add arcjet/skills
```

The `arcjet skills` and `arcjet skills install` commands are breadcrumbs — they
print this recommendation when an agent lands on the CLI without skills
installed. They no longer write files or ship embedded documentation.

Run guided project setup to authenticate, pick a site, and write `ARCJET_KEY`
to your `.env`:

```bash
arcjet skills initialize
```

The [Arcjet plugin](https://github.com/arcjet/arcjet-plugin) bundles these
skills (and more) for Claude Code and Cursor — install it with:

```bash
npx plugins add arcjet/arcjet-plugin
```

## Get help

Need help with anything?
[Email us](mailto:support@arcjet.com) or
[join our Discord](https://arcjet.com/discord) to get support from our
engineering team.

## Support

This repository follows the [Arcjet Support Policy](https://docs.arcjet.com/support).

## Security

This repository follows the [Arcjet Security Policy](https://docs.arcjet.com/security).