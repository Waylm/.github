<!-- Logo + Tagline -->
<p align="center">
  <img src="./logo.svg" alt="Waylm Logo" width="180">
</p>

<h1 align="center">Waylm</h1>
<p align="center"><i>Use us for everything.</i></p>
<p align="center">
  One account · Every app · Secure SSO everywhere
</p>

<p align="center">
  <a href="https://your-domain.example"><img alt="Website" src="https://img.shields.io/badge/website-live-informational"></a>
  <a href="https://docs.your-domain.example"><img alt="Docs" src="https://img.shields.io/badge/docs-quickstart-blue"></a>
  <a href="https://status.your-domain.example"><img alt="Status" src="https://img.shields.io/badge/status-up-brightgreen"></a>
  <a href="https://t.me/yourchannel"><img alt="Telegram" src="https://img.shields.io/badge/Telegram-join-blue"></a>
  <a href="./SECURITY.md"><img alt="Security" src="https://img.shields.io/badge/security-policy-critical"></a>
  <a href="./LICENSE"><img alt="License" src="https://img.shields.io/badge/license-Apache--2.0-lightgrey"></a>
</p>

<hr>

## What is Waylm?
Waylm is an **ecosystem** of apps and developer tools with **single sign-on (SSO)** across web, mobile, and desktop.  
Users sign in once; they’re recognized everywhere across the Waylm suite and third-party apps.

- 🔐 **SSO**: OAuth 2.0 / OpenID Connect (OIDC), optional SAML 2.0
- 🧩 **Pluggable**: drop-in SDKs for JS/TS, iOS, Android, Go, Python
- 🌍 **Everywhere**: first-party apps + partner integrations
- 🪪 **Identity**: MFA, WebAuthn, device trust, org policies
- 🇺🇿 **Global-ready**: reliable for users in Uzbekistan and worldwide

<hr>

## Apps in the Waylm Ecosystem
<p align="center">
  <img src="./apps/app1.svg" alt="App One" width="64">&nbsp;&nbsp;&nbsp;
  <img src="./apps/app2.svg" alt="App Two" width="64">&nbsp;&nbsp;&nbsp;
  <img src="./apps/app3.svg" alt="App Three" width="64">&nbsp;&nbsp;&nbsp;
  <img src="./apps/app4.svg" alt="App Four" width="64">
</p>

| App | What it does | Links |
|---|---|---|
| **App One** | Team workspaces with live collaboration | [Web](#) · [iOS](#) · [Android](#) |
| **App Two** | Secure file hub with org sharing | [Web](#) · [Desktop](#) |
| **App Three** | Realtime chat with org directories | [Web](#) · [Mobile](#) |
| **App Four** | Analytics across your Waylm apps | [Web](#) |

> Want your app here? See **[Integrations →](#integrations)**

<hr>

## SSO at a glance
- **Protocols:** OIDC (Auth Code + PKCE), OAuth 2.0, optional SAML 2.0
- **Security:** MFA, TOTP, WebAuthn/passkeys, IP & device policies
- **Org features:** SCIM user provisioning, role mapping, groups

**Quick flow**
1. User clicks **“Continue with Waylm”**  
2. Waylm handles auth (MFA if required)  
3. Your app receives an **ID token** + **access token**  
4. You verify the token and create a session

```bash
# Example env for your app
WAYLM_ISSUER="https://auth.your-domain.example"
WAYLM_CLIENT_ID="YOUR_CLIENT_ID"
WAYLM_REDIRECT_URI="https://yourapp.example/callback"
WAYLM_SCOPES="openid profile email offline_access"
// Minimal OIDC code sample (Node/Next.js pseudo)
import { Issuer } from 'openid-client';

const waylm = await Issuer.discover(process.env.WAYLM_ISSUER);
const client = new waylm.Client({
  client_id: process.env.WAYLM_CLIENT_ID,
  redirect_uris: [process.env.WAYLM_REDIRECT_URI],
  response_types: ['code'],
});

// 1) Send users to auth
// 2) Handle callback, exchange code -> tokens
```
<hr>
