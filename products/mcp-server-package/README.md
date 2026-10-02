# @cosai-labs/toolpipe-mcp-server

MCP (Model Context Protocol) server for [ToolPipe](https://toolpipe.dev), exposing 55 developer utility APIs to AI agents over stdio.

## Tools Included

| # | Tool | Description |
|---|------|-------------|
| 1 | `json_format` | Format, validate, pretty-print JSON |
| 2 | `generate_qr_code` | Generate QR code image URLs |
| 3 | `generate_hash` | MD5, SHA-1, SHA-256, SHA-512 hashing |
| 4 | `generate_uuid` | Generate UUIDs (v4) |
| 5 | `base64` | Encode/decode Base64 strings |
| 6 | `markdown_to_html` | Convert Markdown to HTML |
| 7 | `shorten_url` | Shorten long URLs |
| 8 | `regex_test` | Test regex patterns against text |
| 9 | `text_stats` | Word count, reading time, etc. |
| 10 | `jwt_decode` | Decode JWT tokens |
| 11 | `dns_lookup` | DNS record lookups (A, MX, TXT, etc.) |
| 12 | `http_headers` | Check HTTP response headers |
| 13 | `ssl_check` | Inspect SSL/TLS certificates |
| 14 | `generate_password` | Generate strong random passwords |
| 15 | `lorem_ipsum` | Generate placeholder text |
| 16 | `convert_color` | Convert between HEX, RGB, HSL |
| 17 | `parse_cron` | Parse cron expressions to human-readable text |
| 18 | `convert_timestamp` | Convert Unix timestamps and ISO dates |
| 19 | `csv_to_json` | Convert CSV data to JSON |
| 20 | `minify_code` | Minify JavaScript, CSS, or HTML |
| 21 | `code_review` | Review code for bugs, security, best practices |
| 22 | `code_explain` | Explain code in plain English |
| 23 | `code_format` | Format/beautify code in many languages |
| 24 | `generate_fake_data` | Generate realistic mock data (names, emails, etc.) |
| 25 | `json_schema_validate` | Validate JSON against a JSON Schema |
| 26 | `whois_lookup` | WHOIS domain registration info |
| 27 | `generate_dockerfile` | Generate Dockerfiles for any language/framework |
| 28 | `generate_docker_compose` | Generate docker-compose.yml for multi-service stacks |
| 29 | `generate_commit_message` | Generate conventional git commit messages |
| 30 | `generate_regex` | Generate regex from natural language |
| 31 | `sql_format` | Format and beautify SQL queries |
| 32 | `json_to_typescript` | Generate TypeScript interfaces from JSON |
| 33 | `jwt_create` | Create signed JWT tokens |
| 34 | `web_extract` | Extract structured content from URLs |
| 35 | `prompt_engineer` | Improve and optimize LLM prompts |
| 36 | `ip_lookup` | Look up IP address information |
| 37 | `crypto_prices` | Get current cryptocurrency prices |
| 38 | `screenshot` | Capture a website screenshot |
| 39 | `http_request` | Send an HTTP request through the API |
| 40 | `seo_analyze` | Analyze a page for SEO metadata |
| 41 | `url_encode_decode` | Encode or decode URL components |
| 42 | `html_encode_decode` | Encode or decode HTML entities |
| 43 | `text_diff` | Compare two text values |
| 44 | `detect_language` | Identify the language of text |
| 45 | `is_website_down` | Check whether a website is available |
| 46 | `domain_intel` | Inspect domain and DNS intelligence (API key required) |
| 47 | `web_structured_extract` | Extract structured data from a web page (API key required) |
| 48 | `web_compare` | Compare web page content (API key required) |
| 49 | `bulk_url_check` | Check multiple URLs (API key required) |
| 50 | `web_monitor` | Monitor a website for changes (API key required) |
| 51 | `api_test_suite` | Run an API endpoint test suite (API key required) |
| 52 | `sitemap_parse` | Parse a website sitemap (API key required) |
| 53 | `robots_check` | Inspect robots.txt directives (API key required) |
| 54 | `bulk_dns_lookup` | Look up DNS for multiple domains (API key required) |
| 55 | `bulk_hash` | Generate hashes for multiple values (API key required) |

## Installation

### Claude Desktop

Add to your `claude_desktop_config.json`:

```json
{
  "mcpServers": {
    "toolpipe": {
      "command": "npx",
      "args": ["-y", "@cosai-labs/toolpipe-mcp-server"],
      "env": {
        "TOOLPIPE_API_KEY": "your-api-key-here"
      }
    }
  }
}
```

### Claude Code

```bash
claude mcp add toolpipe -- npx -y @cosai-labs/toolpipe-mcp-server
```

### Cursor / Windsurf / Other MCP Clients

```json
{
  "toolpipe": {
    "command": "npx",
    "args": ["-y", "@cosai-labs/toolpipe-mcp-server"]
  }
}
```

### Direct Usage

```bash
npm config set @cosai-labs:registry https://npm.pkg.github.com
# Add a GitHub token with read:packages access to ~/.npmrc:
# //npm.pkg.github.com/:_authToken=YOUR_GITHUB_TOKEN
npx @cosai-labs/toolpipe-mcp-server
```

The GitHub Packages registry requires authentication even for public package
downloads. Without that registry mapping and token, npm will look on the public
npm registry, where this package is not currently published.

## Environment Variables

| Variable | Description | Default |
|----------|-------------|---------|
| `TOOLPIPE_BASE_URL` | API base URL | `https://toolpipe.dev` |
| `TOOLPIPE_API_KEY` | API key for higher rate limits | (none, free tier) |

The published package is available from GitHub Packages. Configure npm with the
GitHub Packages registry and an authorized token before installing it if your
client does not already have that registry configured.

## Pricing

- **Free**: 100 API calls per day, no signup required
- **Pro**: 10,000 API calls per day for $9.99/month
- **Enterprise**: 100,000 API calls per day for $49.99/month

Pay with crypto (BTC, ETH, USDT, SOL). No KYC required.

Get an API key at [https://toolpipe.dev](https://toolpipe.dev).

## Why ToolPipe?

- **55 tools in one package**: No need to install multiple MCP servers
- **Works out of the box**: No API key needed for free tier
- **AI-agent friendly**: Designed for Claude, GPT, and other LLM agents
- **Fast**: Sub-100ms response times for most tools
- **Reliable**: 99.9% uptime, rate-limited to prevent abuse

## Requirements

- Node.js 18 or later

## Publishing

The package currently publishes to GitHub Packages under
`@cosai-labs/toolpipe-mcp-server`. Installing it requires a GitHub token with
`read:packages`; publishing requires a token with package write access. The
package is not published to the public npm registry yet.

## License

MIT
