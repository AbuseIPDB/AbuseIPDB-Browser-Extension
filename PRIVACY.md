# Privacy Policy — AbuseIPDB Browser Extension

_Last updated: 2026-07-27_

## Summary

This extension sends the IP addresses and text you explicitly submit to the
AbuseIPDB API, and stores your AbuseIPDB API key locally in your browser. It
collects nothing else, contains no analytics, and transmits nothing to any server
other than `abuseipdb.com`.

## What the extension stores, and where

All storage is local to your browser (`storage.local`). Nothing is synced to
another device and nothing is transmitted to us.

| Stored value | Purpose | Cleared by |
| --- | --- | --- |
| `apiKey` | Your AbuseIPDB API key, sent as the `Key` header on API requests | "Remove Key" in the extension settings |
| `checkPrefill` | The last value you looked up, so the popup reopens with it | The reset button in the popup |
| `lastResult` | The last lookup result, so the popup reopens showing it | The reset button in the popup |

Your API key is stored in plain text in browser extension storage. That is the
only mechanism the WebExtension platform provides for an extension that must send
the key on every request. Anyone with access to your browser profile can read it,
so treat it as you would a saved password, and revoke it at
<https://www.abuseipdb.com/account/api/keys> if your machine is compromised.

## What the extension sends, and where

Requests go only to `https://api.abuseipdb.com`. There are three:

- **`GET /api/v2/account`** — sent when you validate a key in settings. Carries
  your API key. Returns your account label and API usage limits.
- **`GET /api/v2/check`** — sent when you check an IP, either from the popup or
  from the right-click "Check with AbuseIPDB" menu. Carries your API key and the
  IP address or text you selected.
- **`POST /api/v2/report`** — sent only when you fill in the report form and press
  Submit. Carries your API key, the IP address, the categories you selected, and
  the comment you wrote.

Text is transmitted **only** when you explicitly act: pressing Check, choosing a
right-click menu item, or pressing Submit. The extension does not read page
content, does not run content scripts, and does not observe your browsing.

Data sent to AbuseIPDB is handled under the AbuseIPDB privacy policy at
<https://www.abuseipdb.com/legal>. Reports you submit are published to the
AbuseIPDB database as described there — do not put private information in a
report comment.

## What the extension does not do

- No analytics, telemetry, crash reporting, or usage tracking. The one network
  rule the extension declares rewrites its own outgoing `User-Agent` header; it
  observes nothing and reports nothing.
- No content scripts; no access to the pages you visit.
- No remotely-hosted code. All JavaScript is bundled into the package.
- No advertising, no data brokering, no sale or transfer of data to third
  parties.
- No use of your data to determine creditworthiness or for lending purposes.

## Permissions, and why each is needed

| Permission | Why |
| --- | --- |
| `storage` | Save your API key and the last lookup locally |
| `contextMenus` | Add the right-click "Check" / "Report" / "Open check page" items |
| `notifications` | Show the result of a right-click check, and tell you when a check fails |
| `declarativeNetRequestWithHostAccess` | Append `AbuseIPDB Browser Extension/1.0` to the `User-Agent` header on requests to `api.abuseipdb.com`, so API traffic from this extension is identifiable. Your browser's own User-Agent is preserved, not replaced. The rule is static, declared in `rules.json`, and scoped to that one host. This permission cannot read request or response contents, and the `WithHostAccess` variant only acts on hosts the extension already has permission for |
| `https://api.abuseipdb.com/*` | Call the API |
| `https://www.abuseipdb.com/*` | Open the AbuseIPDB site when you click through |

## Removing your data

Removing the extension deletes its local storage. To revoke the key itself,
delete it at <https://www.abuseipdb.com/account/api/keys>.

## Contact

Questions about this policy: <bsebring@marathon-studios.com>
