# Cf Crawl

"Crawl entire websites using Cloudflare Browser Rendering /crawl API. Initiates async crawl jobs, polls for completion, and saves results as markdown files. Useful for ingesting documentation sites, knowledge bases, or any web content into your project context. Requires CLOUDFLARE_ACCOUNT_ID and CLOUDFLARE_API_TOKEN environment variables."

## Overview

This repository preserves the AITMPL skill definition and all companion resources published with it.

## Installation

```bash
git clone https://github.com/Brajesh31/claude-cf-crawl-skill.git ~/.claude/skills/cf-crawl
```

On Windows, use `%USERPROFILE%\.claude\skills\cf-crawl` as the destination.

## Usage

Claude Code can load this skill when a request matches its description. Invoke directly with `/cf-crawl` when needed.

## Repository structure

```text
cf-crawl/
├── SKILL.md
├── README.md
└── LICENSE
```

## Runtime requirements

- No build step is required for the instruction file.
- Confirm external service credentials and configuration before running automation scripts.
- Scripts and tests are not represented as executed.
