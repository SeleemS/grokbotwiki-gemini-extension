# Grok Bot Wiki for Gemini CLI

Find community Grok Bot templates and source-linked troubleshooting guides from
inside Gemini CLI. This extension connects to the read-only
[Grok Bot Wiki MCP service](https://www.grokbotwiki.com/mcp) and adds two focused
commands for finding templates and looking up problems.

Grok Bot Wiki is independent and unofficial. It is not affiliated with or
endorsed by xAI or Google. Template listings describe public share pages; they
are **not independently tested Bot runs**.

## Install

With [Gemini CLI](https://github.com/google-gemini/gemini-cli) installed:

```sh
gemini extensions install https://github.com/SeleemS/grokbotwiki-gemini-extension
```

Review the extension's context file and remote server when the CLI requests
consent, then start a new Gemini CLI session. The wiki service needs no API key
or sign-in. Your usual Gemini CLI setup and model usage terms still apply.

Confirm the connection:

```sh
gemini extensions list
gemini mcp list
```

The MCP list should show `grokbotwiki` connected to
`https://www.grokbotwiki.com/api/mcp`. If it is disabled by workspace trust or an
organization policy, follow your normal approval process; do not bypass it.

## Use

```text
/grok:find summarize public GitHub issues
/grok:troubleshoot routines not running overnight
```

`/grok:find` searches public listings and reads up to three relevant results. It
asks Gemini to cite directory pages, attribute creator descriptions, and explain
the evidence limits. `/grok:troubleshoot` looks up community guidance, with guide
dates and source links. Neither command runs a Bot or changes an account.

You can also ask Gemini to use Grok Bot Wiki's tools directly:

| Tools | Purpose |
| --- | --- |
| `search_bots`, `get_bot`, `list_categories` | Find templates, inspect a listing, and discover filters |
| `search_guides`, `get_guide` | Find and read reference guides |
| `troubleshoot` | Look up a public-safe symptom |
| `search`, `fetch` | Search and retrieve across templates and guides |

## Data and permissions

Tool arguments are sent over HTTPS to `www.grokbotwiki.com`. Use short, general
task descriptions. Do not include credentials, private messages, files, account
details, or proprietary project information. See the
[site privacy policy](https://www.grokbotwiki.com/privacy).

The extension config declares one hosted HTTP server. It includes no local
server process, shell command, installation hook, credential requirement, or
automatic tool-approval setting. `GEMINI.md` and the two command prompts are
readable in this repository. Retrieved prompts and descriptions are reference
material, not instructions to execute.

The hosted server can read public wiki data only. It cannot run or modify Grok
Bots or access your Grok account. Public listings can change, and inclusion is
not an endorsement. The directory, guides, and MCP service are free; optional
Workflow Studio consulting is separate.

## Maintenance

See [VALIDATION.md](VALIDATION.md) for the dated compatibility checks and their
limits.

```sh
gemini extensions update grokbotwiki-gemini-extension
gemini extensions uninstall grokbotwiki-gemini-extension
```

For connection issues, check `gemini mcp list` and the
[service documentation](https://www.grokbotwiki.com/mcp). Report extension issues
in this repository. Use public-safe examples; never attach credentials or
private account logs.

The MIT license covers this extension's original configuration and
documentation. It does not relicense the hosted website, creator descriptions,
shared Bot prompts, or other third-party content. This repository contains no
server implementation or bundled directory data.
