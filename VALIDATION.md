# Compatibility checks

Checked October 7, 2026 with Gemini CLI **0.63.0**, Node.js **22.22.0**, and
macOS. The CLI was obtained from the official `@google/gemini-cli` npm package.
Testing used an isolated `GEMINI_CLI_HOME`, with no model account or API key.

- Gemini CLI accepted the extension manifest, installed it from its local
  directory, and listed version `0.1.0` with the context file and `grokbotwiki`
  server enabled.
- `gemini mcp list` reported the hosted HTTP server **Connected**.
- Installation from the public GitHub URL also succeeded, followed by extension
  listing and a connected MCP check. This used a fresh temporary profile and the
  CLI's file-based storage option to keep test state separate from the OS
  keychain. Extension integrity validation remained enabled.
- Both command files parsed as TOML and contain no shell or file interpolation.
- Separate read-only MCP checks completed initialization and tool discovery.
  The service advertised eight tools with read-only annotations.
- Public template search and detail retrieval succeeded. Guide search, guide
  retrieval, and troubleshooting also succeeded, including full-guide retrieval
  using the final path segment of a troubleshooting result's guide URL.
- Results included source URLs and the template evidence limitation. No Bot was
  executed and no account was accessed or changed.

These checks establish extension loading, connection, and public-data retrieval
at the recorded date. They do not evaluate model-generated answers or claim
that every Gemini CLI version, platform, organization policy, or shared Bot is
compatible. OS keychain integration was not validated. The slash-command prompts
were syntax checked; no paid or
authenticated model request was made to exercise their generated answers.

To check a normal installation, use `gemini extensions list` and `gemini mcp
list`, then try the README examples with public-safe inputs. Keep normal tool
approval and workspace-trust controls enabled.

Extension format and distribution follow the official
[reference](https://github.com/google-gemini/gemini-cli/blob/main/docs/extensions/reference.md)
and [release guide](https://github.com/google-gemini/gemini-cli/blob/main/docs/extensions/releasing.md).
