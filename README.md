# AbuseIPDB Browser Extension

Check and report IP addresses against [AbuseIPDB](https://www.abuseipdb.com) without leaving the web page.

AbuseIPDB is a community-driven database of IP addresses reported for hacking attempts, spam, DDoS attacks and other abuse. This extension puts that data one click away in your browser.

- **Check an IP** — paste it into the popup, or highlight it on any page, right-click, and choose *Check with AbuseIPDB*. The toolbar icon turns green, orange or red with the result, and the popup shows the abuse confidence score, risk tier, report count, country, ISP, usage type and last-reported date.
- **Report an IP** — highlight it, right-click, choose *Report with AbuseIPDB*, pick one or more abuse categories, add a comment, and submit.
- **Track your quota** — Settings shows your plan tier and how much of your daily check and report allowance is left.

Works in Chrome, Edge and other Chromium browsers. Also available for Firefox.

## Getting started

The extension uses **your own AbuseIPDB API key**. A free account is all you need.

### 1. Create a free AbuseIPDB account

1. Go to <https://www.abuseipdb.com/register>.
2. Fill in a username, email address and password, then submit the form.
3. Open the confirmation email from AbuseIPDB and click the verification link. You must verify your email before you can create an API key.

### 2. Generate an API key

1. Sign in and go to <https://www.abuseipdb.com/account/api/keys>.
2. Click **Create Key**.
3. Give the key a name (for example `browser-extension`) and confirm.
4. Copy the key. Keep it private — it acts as your password for the API.

### 3. Add the key to the extension

1. Click the AbuseIPDB icon in your browser toolbar.
2. Open **Settings**.
3. Paste the key into the **AbuseIPDB API Key** field and save.

Settings will now show your plan tier and remaining daily allowance. You're ready to check and report IPs.

## Free plan limits

| | Free account | Verified webmaster |
| --- | --- | --- |
| IP checks per day | 1,000 | 3,000 |
| IP reports per day | 1,000 | 3,000 |

Daily usage resets at 00:00 UTC. Each check and each report uses one request.

Verified webmasters get the higher limit by proving ownership of a domain (HTML file, meta tag or DNS TXT record) at <https://www.abuseipdb.com/account/webmasters>. Paid plans with higher limits are listed at <https://www.abuseipdb.com/pricing>.

## Privacy

The extension only talks to `api.abuseipdb.com`, and only when you press Check, Submit, or pick a right-click menu item. It does not read the pages you visit, run content scripts, or collect analytics. Your API key is stored locally in your browser and is never sent anywhere except AbuseIPDB.

Full details: [PRIVACY.md](PRIVACY.md).

## Support

Questions or problems: <support@abuseipdb.com>
