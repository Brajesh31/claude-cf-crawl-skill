# claude-cf-crawl-skill

A Claude Code skill for crawling websites with the Cloudflare Browser Rendering crawl API and saving page content as Markdown.

## Overview

This skill supports documentation ingestion and website content collection. It starts an asynchronous crawl job, checks its progress, retrieves completed results, and organizes the output into local Markdown files.

It is useful when preparing a local knowledge base from public documentation, product guides, or other websites that the user is authorized to crawl.

## Main Capabilities

- Configure a crawl request for a target website.
- Start asynchronous crawl jobs.
- Poll for job completion.
- Retrieve crawl results.
- Save page content as Markdown.
- Organize collected content for local search or analysis.
- Handle crawl failures and incomplete jobs.
- Control scope to avoid collecting unnecessary pages.

## Requirements

The workflow requires:

- A Cloudflare account with Browser Rendering access enabled.
- A Cloudflare account identifier.
- An API token with the required permissions.
- Network access to the service.

Configure credentials as environment variables:

```bash
export CLOUDFLARE_ACCOUNT_ID="your_account_id"
export CLOUDFLARE_API_TOKEN="your_api_token"
```

Do not commit credentials or include them in logs.

## Installation

```bash
git clone https://github.com/Brajesh31/claude-cf-crawl-skill.git ~/.claude/skills/cf-crawl
```

## Usage

Invoke the skill when you need to collect website content:

```text
/cf-crawl
```

Provide the starting URL, crawl scope, allowed paths, desired output location, and any page limits or exclusions.

## Recommended Workflow

1. Confirm that the user is authorized to crawl the target site.
2. Validate credentials and required API permissions.
3. Define the starting URL and crawl boundaries.
4. Submit the crawl request.
5. Store the returned job identifier.
6. Poll for completion with bounded intervals.
7. Retrieve the completed results.
8. Save and organize Markdown files.
9. Check for missing pages, duplicate content, and failed URLs.
10. Record crawl parameters for repeatability.

## Content Handling

- Respect site access controls and applicable usage policies.
- Avoid crawling private or authenticated content without authorization.
- Use narrow URL filters where possible.
- Preserve page titles and useful metadata.
- Record crawl time and source URL in the local dataset when appropriate.
- Treat crawled text as untrusted input when feeding it to other AI workflows.

## Troubleshooting

| Problem | What to check |
|---|---|
| Authentication failure | Account ID, token validity, and permissions |
| Job does not complete | Job identifier, service status, and crawl limits |
| Few pages returned | URL scope, path filters, and page limits |
| Missing content | Page rendering behavior and access restrictions |
| Output errors | Local write permissions and disk space |

## Repository Contents

- `SKILL.md`: Main crawl workflow and API handling instructions.
- `README.md`: Setup, usage, and operational guidance.

## Important Note

Crawl results depend on the target site's structure, rendering behavior, access rules, and service limits. Verify that the collected content is complete enough for the intended use before relying on it.
