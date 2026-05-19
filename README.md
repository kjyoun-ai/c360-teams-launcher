# c360-teams-launcher

Minimum-viable launcher for embedding C360 Analyst (MAS chat) inside a Microsoft Teams personal tab.

Hosted on GitHub Pages because the Databricks Apps reverse-proxy OAuth flow doesn't survive Teams' Electron webview when the app domain is loaded directly in an iframe (zero requests reach the app from Teams). The launcher uses `microsoftTeams.authentication.authenticate({url})` to open the Databricks app in a popup that shares Teams' cookie jar, so that after the popup closes the iframe can load with valid auth cookies.

This is a diagnostic/MVP build. If the popup-cookie pattern works, this will be rebuilt under a Flexera-controlled origin for production.
