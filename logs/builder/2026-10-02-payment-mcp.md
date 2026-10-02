# Builder Update - 2026-10-02

## Findings

- OxaPay invoice creation and HMAC-SHA512 webhook verification already exist in `products/api-service/main.py`.
- The API can fall back to NOWPayments or direct-wallet payment instructions. OxaPay account signup remains blocked by the reCAPTCHA noted in the prior handoff; no merchant key is present in repository code.
- `products/mcp-server-package` already contains a 55-tool MCP server package and Smithery configuration. Its configured registry is GitHub Packages, not public npm.

## Changes

- Added `GET /payments/providers` to report configured gateway names and preferred checkout without disclosing credentials.
- Documented OxaPay environment configuration and callback requirements in the API README.
- Corrected the MCP README's stale 35-tool count and clarified GitHub Packages installation/publication status.

## Outstanding

- Complete OxaPay signup and set `OXAPAY_MERCHANT_KEY` in the deployed API environment.
- Public npm publication and marketplace submissions require registry/platform credentials and were not performed in this repository-only step.
- Git pull, commit, and push were unavailable because `.git/FETCH_HEAD` is read-only in this environment.
