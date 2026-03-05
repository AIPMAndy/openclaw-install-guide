**English** | [简体中文](README.md)

<div align="center">

# OpenClaw Installation Guide

**Install OpenClaw and connect AICodeMirror (Claude/GPT/Gemini) in 10 minutes**

[![Stars](https://img.shields.io/github/stars/AIPMAndy/openclaw-install-guide?style=social)](https://github.com/AIPMAndy/openclaw-install-guide/stargazers)
[![License](https://img.shields.io/badge/license-MIT-green)](LICENSE)
[![Platforms](https://img.shields.io/badge/platform-macOS%20%7C%20Linux%20%7C%20Windows-blue)](#)

<img src="assets/demo.gif" alt="OpenClaw install and model setup demo" width="920" />

</div>

## Invite Link

- AICodeMirror invite link:
  https://www.aicodemirror.com/register?invitecode=EZUWFL

## Why This Guide

| Item | Official Docs | This Guide |
|---|---|---|
| OS coverage | Split information | One page for `MacOS/Linux + Windows` |
| Onboarding choices | Abstract | Recommended options included |
| Model integration | Need manual mapping | Copy-ready `models` template |
| Verification | Trial and error | Short validation path |

## 30-Second Quick Start

### MacOS/Linux

```bash
curl -fsSL https://openclaw.ai/install.sh | bash
openclaw onboard --install-daemon
```

### Windows (PowerShell)

```powershell
iwr -useb https://openclaw.ai/install.ps1 | iex
openclaw onboard
```

## Contents

- [Official Links](#official-links)
- [Install Steps](#install-steps)
- [Recommended Onboarding Options](#recommended-onboarding-options)
- [Configure AICodeMirror Providers](#configure-aicodemirror-providers)
- [Restart and Verify](#restart-and-verify)
- [Telegram Bot Integration (Optional)](#telegram-bot-integration-optional)
- [Launch Copy Pack](#launch-copy-pack)
- [FAQ](#faq)
- [Source Tutorials](#source-tutorials)

## Official Links

- OpenClaw website: https://openclaw.ai/
- OpenClaw project: https://github.com/openclaw/openclaw

## Install Steps

### MacOS/Linux

```bash
curl -fsSL https://openclaw.ai/install.sh | bash
openclaw onboard --install-daemon
```

### Windows

```powershell
iwr -useb https://openclaw.ai/install.ps1 | iex
openclaw onboard
```

## Recommended Onboarding Options

During `openclaw onboard`, use these choices:

- Risk prompt: `yes`
- Install mode: `Quick Install`
- Model setup: `Skip` for now
- Provider filter: `Google` first is fine
- Bot setup: `Skip` for now
- Built-in skills: `yes`
- Skills installer: `pnpm`
- Skills API keys: `No` for now

## Configure AICodeMirror Providers

Merge `config/openclaw.models.json` into your local `openclaw.json` under `models.providers`.

- MacOS/Linux path: `~/.openclaw/openclaw.json`
- Windows path: `C:\Users\YOUR_USERNAME\.openclaw\openclaw.json`
- Template file: [`config/openclaw.models.json`](config/openclaw.models.json)

> Replace every `换成你的key` with your real API key.

## Restart and Verify

### Restart gateway

- MacOS/Linux:

```bash
openclaw gateway restart
```

- Windows:

```powershell
openclaw gateway
```

### Validate in chat UI

```text
/models
/models aicodemirror-claude
/model aicodemirror-claude/claude-opus-4-5-20251101
hello
```

If the model responds successfully, setup is done.

## Telegram Bot Integration (Optional)

1. Create a bot with `BotFather` using `/newbot` and get the token.
2. Open local gateway page: `Config -> Channels -> Telegram Bot Token`, then paste token.
3. Set your local proxy (example: `http://127.0.0.1:7890`).
4. Get pairing code and run:

```bash
openclaw pairing approve telegram YOUR_PAIRING_CODE
```

5. Chat with your bot in Telegram to confirm it works.

## Launch Copy Pack

- Ready-to-post Chinese/English launch copy:
  [`docs/launch-copy.md`](docs/launch-copy.md)
- Channels included: `X`, `Reddit`, `Hacker News`

## FAQ

### 1. `/models` does not show AICodeMirror providers

- Check your `openclaw.json` structure (`models.providers` path).
- Check whether API keys are replaced.
- Restart gateway again.

### 2. Provider appears but model call fails

- Check network/proxy.
- Verify `api` field matches template.
- Verify model id spelling.

### 3. No effect on Windows

- Run commands in `PowerShell` (not CMD).
- Retry as Administrator.

## Source Tutorials

- MacOS/Linux:
  https://furbox.yuque.com/org-wiki-furbox-spmbkw/oishf7/lpqfodgg3qwhxbsa
- Windows:
  https://furbox.yuque.com/org-wiki-furbox-spmbkw/oishf7/lzsgqkrtgit6eo17

---

If this guide saves you time, a Star is appreciated:
https://github.com/AIPMAndy/openclaw-install-guide
