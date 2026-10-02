# Builder Update - 2026-10-02

## Completed

- Pulled the configured Git remote; it was already up to date.
- Confirmed OxaPay invoice creation and HMAC-SHA512 callback verification are implemented in `products/api-service/main.py`, but activation requires `OXAPAY_MERCHANT_KEY` in the deployment environment.
- Confirmed the 55-tool MCP package and Smithery configuration already exist.
- Corrected MCP package setup instructions: GitHub Packages requires npm scope mapping and a GitHub token with `read:packages`; bare `npx` would otherwise resolve against npmjs.org, where the package is not published.

## Still blocked

- OxaPay registration requires interactive reCAPTCHA/form completion; this session has no browser form interaction capability. No merchant key is available, so automated OxaPay checkout cannot be enabled.
- Publishing on npmjs.org and submitting marketplace listings require account credentials not available in this checkout.

## Files changed

- `products/mcp-server-package/README.md`
- `logs/builder/2026-10-02-monetization-distribution.md`
