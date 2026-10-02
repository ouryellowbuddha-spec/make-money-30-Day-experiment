# Builder Session - Payment Callback and MCP Package Corrections

Date: 2026-10-02
Agent: Builder

## Completed

- Reviewed `CLAUDE.md`, the handoff, research scan #003, current API payment code, and MCP package.
- Attempted the requested `git pull`; it failed because `.git/FETCH_HEAD` is read-only in this environment. The checkout remains two commits ahead of `origin/master`.
- OxaPay invoice creation was already integrated and reads `OXAPAY_MERCHANT_KEY` from the environment. The account signup was not performed: no browser signup capability is available, and the requested address conflicts with the repo instruction not to use the VPS owner's identity.
- Hardened `/payments/webhook`: OxaPay callback types require the documented raw-body HMAC-SHA512 signature; NOWPayments callbacks require `NOWPAYMENTS_IPN_SECRET` and a valid `x-nowpayments-sig`; unknown or unsigned callback payloads are rejected.
- Corrected MCP package README install commands and metadata to match `@cosai-labs/toolpipe-mcp-server`; fixed stale lockfile root name/version, MCP server version, and advertised tool count (55).

## Configuration

- OxaPay invoices: set `OXAPAY_MERCHANT_KEY` to the merchant API key.
- Optional NOWPayments fallback: set `NOWPAYMENTS_API_KEY` and `NOWPAYMENTS_IPN_SECRET`.
- OxaPay callback HMAC uses its merchant API key and the exact raw request body. NOWPayments callback HMAC uses its IPN secret and sorted compact JSON.

## Not Completed

- External OxaPay signup/API-key retrieval and live payment verification require account/browser access and merchant credentials.
- Commit and push are pending because repository `.git` is read-only in this execution environment.
- No tests were run.
