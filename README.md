Koanyx WP Scanner — WordPress Reconnaissance & Vulnerability Mapper
Koanyx WP Scanner is a browser extension that passively fingerprints WordPress sites, enumerates exposed usernames, detects installed plugins, and maps them against known CVEs — all in one lightweight popup.

Fast. Passive. Insightful. Built for security researchers, penetration testers, and blue/red teams.

Installation (Load Unpacked)

Koanyx WP Scanner is a Manifest V3 extension distributed as source, not through a web store — so it's loaded as an unpacked extension. Steps are nearly identical across Chromium-based browsers, with Firefox handled separately below.

0. Get the code (all browsers)
bash
git clone https://github.com/<your-username>/Koanyx-WP-Scanner.git

Or download the ZIP from GitHub (Code → Download ZIP) and extract it somewhere permanent — the folder must stay in place, since Chromium browsers load the extension directly from it (it isn't copied anywhere).

Google Chrome
Open chrome://extensions/
Toggle Developer mode on (top-right corner)
Click Load unpacked
Select the extracted Koanyx-WP-Scanner folder (the one containing manifest.json)
The shield icon appears in the toolbar — click the puzzle-piece icon and pin it for easy access

Microsoft Edge
Open edge://extensions/
Toggle Developer mode on (left sidebar)
Click Load unpacked
Select the Koanyx-WP-Scanner folder
Pin it from the extensions (puzzle-piece) menu

Brave
Open brave://extensions/
Toggle Developer mode on (top-right corner)
Click Load unpacked
Select the Koanyx-WP-Scanner folder
Pin it from the extensions menu

Opera
Open opera://extensions/
Toggle Developer mode on (top-right corner)
Click Load unpacked
Select the Koanyx-WP-Scanner folder

Vivaldi
Open vivaldi://extensions/
Toggle Developer mode on (top-right corner)
Click Load unpacked
Select the Koanyx-WP-Scanner folder

Mozilla Firefox (temporary install)
Firefox doesn't support permanently loading unsigned Manifest V3 extensions from disk — only a temporary load that lasts until Firefox is closed:

Open about:debugging#/runtime/this-firefox
Click Load Temporary Add-on…
Select any file inside the Koanyx-WP-Scanner folder, e.g. manifest.json
The extension loads immediately but is removed when Firefox restarts — repeat these steps each session, or package it with web-ext build and submit it to Mozilla for a signed, permanent install
Updating

To update after pulling new changes, just git pull in the cloned folder, then go back to chrome://extensions/ (or the equivalent page) and click the reload (⟳) icon on the Koanyx WP Scanner card — no need to remove and re-add it.

Uninstalling
Go to the browser's extensions page, find Koanyx WP Scanner, and click Remove. Deleting the local folder alone does not uninstall it from the browser.

 How It Works
WordPress Detection
Meta generator tag (<meta name="generator" content="WordPress X.X">)
/wp-content/ and /wp-includes/ directory references
/wp-json/ REST API endpoints
Plugin Detection
Script/stylesheet tags referencing /wp-content/plugins/
Version parameters in query strings (?ver=X.X.X)
Inline HTML references to plugin assets
Vulnerability Checking
Plugin CVE database — maps plugin slugs to known CVE records
WordPress core CVE database — 50+ core vulnerabilities with affected version ranges
Version comparison logic — matches the detected site version against vulnerable ranges
Username Enumeration
DOM parsing — scans for author links in page HTML
REST API — queries /wp-json/wp/v2/users
Author archives — tests /?author=1,2,3 redirects

 Design
Koanyx WP Scanner ships with a mahogany color theme (light and dark) and a dedicated shield-style icon set (16/32/48/128px) with green/red status indicators shown in the toolbar depending on whether WordPress was detected.

 Disclaimer
This tool is intended solely for educational, research, and authorized security testing purposes.
You must have explicit permission to analyze any website you do not own.
Koanyx WP Scanner does not exploit vulnerabilities — it only identifies publicly available information.
The athor and contributors are not responsible for misuse or legal consequences resulting from unauthorized use.
Always follow ethical hacking standards and applicable laws.

 Use Cases
WordPress security audits
Bug bounty reconnaissance
Red team / blue team assessments
Plugin exposure analysis
Vulnerability research
Cybersecurity education & training

 License
Released under the MIT License.

🙌 Contributing

Issues and pull requests are welcome — especially updates to the CVE database as new WordPress core and plugin vulnerabilities are disclosed.
