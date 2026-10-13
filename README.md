# Jain Wire — Invoice Audit Tools

Two browser-based checkers that compare Tally sales invoices (PDF) against the day's loading plan / rate sheet (Excel).

| Page | Branch | Version |
|---|---|---|
| `calicut/` | Calicut (CLT) | v1.1 |
| `ernakulam/` | Ernakulam (EKM) | v6.0 (web build of v5.2) |

The root `index.html` is a landing page linking to both.

## How it works
- Everything runs in the browser. Bills and Excel files are read locally and never uploaded.
- No server, no API key, no AI calls.
- Rules, code tables and the discrepancy log are saved in the browser (`localStorage`), so they are per browser and per computer.
  - Calicut uses the key `jainwire.clt.audit.v1`.
  - Ernakulam uses keys starting with `jainwire.ekm.`.

## Ernakulam: changes from the Claude version (v5.2 → v6.0)
- Saving switched from Claude's artifact storage to the browser's `localStorage`.
- The AI fallback was removed (it needed an API key, which cannot sit in a public page). A bill the direct reader cannot read now shows a clear "check this bill manually" message.
- `pdf-lib` removed (it was only used before the AI call).
- Claude-specific wording removed; "Ernakulam" added to the header.
- Parsing, matching, tolerances, bundle rules and Tata-wire rules are unchanged.

## Updating a page
1. Open the repo on GitHub and click the file (for example `ernakulam/index.html`).
2. Click the pencil icon, make the change (or paste the new version), and click **Commit changes**.
3. The live site updates in about a minute. Press Ctrl+F5 in the browser to load the new version.
