# Tongs — Remote MCP Server for Android (AI Control)

**Let Claude, ChatGPT, Gemini CLI, or any MCP client control your own Android phone—view the screen, tap, type, swipe, and open apps—with per-app permissions and on-phone approval. No root required.**

> **Note:** This public repository hosts documentation and registry metadata (`server.json`) for the hosted Tongs Remote MCP Server (`https://mcp.tongsapp.com`). The Tongs mobile apps and hosted server are proprietary software.

- **Website:** https://tongsapp.com
- **AI Control Setup Guide:** https://tongsapp.com/connect
- **Getting Started:** https://tongsapp.com/start
- **Community & Support (Discord):** https://discord.gg/Wqbdpmfsjp
- **Support Email:** support@tongsapp.com

---

## What Tongs Does

1. **AI Control (Remote MCP for Android)** — Connect your Android phone (Android 11+, no root) to Claude, ChatGPT, Gemini CLI, or any MCP client via `https://mcp.tongsapp.com`. Ask your assistant to set timers, summarize notifications, adjust settings, or run multi-step tasks on your phone even when you are away. *Only an Android phone is needed.*
2. **Android on iPhone** — Forward your Android's notifications to your iPhone (iOS 17+), reply directly from the notification banner (free), and open end-to-end encrypted remote screen control over Wi-Fi or mobile data.

---

## Quick Setup (Remote MCP)

### 1. Prepare your Android phone
1. Install **Tongs** on your Android phone (Android 11 or later). See [tongsapp.com/start](https://tongsapp.com/start) for download options.
2. Follow the in-app setup wizard to enable Wireless debugging and sign in with Google.

### 2. Connect your MCP client

- **Remote MCP Endpoint:** `https://mcp.tongsapp.com`
- **Transport:** Streamable HTTP (`streamable-http`)
- **Authentication:** OAuth 2.0 (Dynamic Client Registration + PKCE; approve each new connection on your phone)

#### Claude (Web, Mobile, Desktop)
1. Go to **Settings → Connectors**.
2. Add a **Custom Connector** with URL `https://mcp.tongsapp.com`.
3. Sign in and approve the connection on your Android phone.

#### ChatGPT
Add `https://mcp.tongsapp.com` as an MCP connector and follow the step-by-step instructions on [tongsapp.com/connect](https://tongsapp.com/connect).

#### Gemini CLI
```bash
gemini mcp add --transport http --scope user tongs https://mcp.tongsapp.com
```
Then run `/mcp auth` in Gemini CLI and approve the connection on your phone.

#### Claude Code
```bash
claude mcp add --transport http tongs https://mcp.tongsapp.com
```

---

## Permissions & Safety Model

- **OAuth + On-Phone Approval:** Every new client connection must be explicitly approved on your Android phone.
- **Per-App Allowlist:** AI Control operates freely only inside the apps you explicitly allow. Opening any other app prompts you on your phone (`Deny` / `Allow Once` / `Always Allow`).
- **Financial App Protection:** Banking and payment apps that Tongs recognizes **always ask on your phone every time** and cannot be set to always allow.
- **Hidden Verification Codes:** Verification codes are hidden from the assistant.
- **Always Visible & Stoppable:** Your Android screen shows an active indicator with a stop button whenever AI Control is running, and every step is logged.
- **Data Flow:** Screen content passes through Tongs servers strictly to relay it to the assistant you chose; it is not stored. Remote control and notifications between your Android and iPhone are end-to-end encrypted.

---

## Pricing & Requirements

- **Notifications & replies (iPhone + Android):** Free.
- **Remote control & AI Control:** Free to try; Tongs Pro is $4.99/month or $39.99/year.
- **Requirements:** Android 11 or later (no root; tested on Samsung and Pixel, works on most Android phones). For iPhone remote control and notifications, iOS 17 or later.
- **Good to know:**
  - After your Android phone restarts, unlock it and turn Wireless debugging back on.
  - Tongs cannot answer phone calls.

---

## Support & Feedback

- Join our Discord (`#getting-started`, `#ai-control-mcp`, `#bug-reports`): https://discord.gg/Wqbdpmfsjp
- Email: support@tongsapp.com
