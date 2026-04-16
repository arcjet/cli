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

### Homebrew (macOS and Linux)

```bash
brew install arcjet/tap/arcjet
```

### Download a release

Download the latest binary for your platform from
[Releases](https://github.com/arcjet/cli/releases). Extract the archive and
place the `arcjet` binary somewhere on your `PATH`.

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

The `arcjet skills` command provides built-in documentation optimized for AI
coding agents. Skills are shipped with the binary and always match the current
CLI version.

List available topics:

```bash
arcjet skills
```

Show a detailed guide for a specific topic:

```bash
arcjet skills auth
arcjet skills rules
arcjet skills analyze
```

Install the `ARCJET.md` skills file into your project so agents can discover
Arcjet capabilities automatically:

```bash
arcjet skills install
```

Run guided project setup to install the SDK and configure your application:

```bash
arcjet skills initialize
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