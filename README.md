# OpenClaw 安装教程（含 AICodeMirror 配置）

> 本项目为 OpenClaw 的中文安装与配置教程整理版，覆盖 `MacOS/Linux` 与 `Windows`。

## 邀请注册链接

- AICodeMirror 邀请链接：
  https://www.aicodemirror.com/register?invitecode=EZUWFL

## 原始教程来源

- MacOS/Linux 教程：
  https://furbox.yuque.com/org-wiki-furbox-spmbkw/oishf7/lpqfodgg3qwhxbsa
- Windows 教程：
  https://furbox.yuque.com/org-wiki-furbox-spmbkw/oishf7/lzsgqkrtgit6eo17

## 官方地址

- 官网：https://openclaw.ai/
- 项目地址：https://github.com/openclaw/openclaw

## 一、MacOS/Linux 安装

1. 执行安装脚本：

```bash
curl -fsSL https://openclaw.ai/install.sh | bash
```

2. 执行初始化：

```bash
openclaw onboard --install-daemon
```

3. 初始化过程建议：
- 风险提示选择 `yes`
- 安装模式选择 `快速安装`
- 模型配置先 `跳过`
- Provider 筛选可先选 `Google`
- 对话机器人先 `跳过`
- skills 包选择 `yes`
- skills 安装方式选 `pnpm`
- skills 的模型 key 配置可先都选 `No`

## 二、Windows 安装

1. 创建安装目录并在 PowerShell 执行：

```powershell
iwr -useb https://openclaw.ai/install.ps1 | iex
```

2. 执行初始化：

```powershell
openclaw onboard
```

3. 初始化过程建议同上（风险提示 `yes`、快速安装、模型先跳过、skills 选 `pnpm`）。

## 三、配置 AICodeMirror Provider

将以下 `models` 配置写入 `openclaw.json`：

- MacOS/Linux 路径：`~/.openclaw/openclaw.json`
- Windows 路径：`C:\Users\你的用户名\.openclaw\openclaw.json`

> 请把下面所有 `apiKey` 的 `换成你的key` 改成你自己的真实 Key。

```json
{
  "models": {
    "providers": {
      "aicodemirror-claude": {
        "baseUrl": "https://api.aicodemirror.com/api/claudecode",
        "apiKey": "换成你的key",
        "api": "anthropic-messages",
        "models": [
          {
            "id": "claude-sonnet-4-5-20250929",
            "name": "Claude Sonnet 4.5"
          },
          {
            "id": "claude-opus-4-5-20251101",
            "name": "Claude Opus 4.5"
          }
        ]
      },
      "aicodemirror-gpt": {
        "baseUrl": "https://api.aicodemirror.com/api/codex/backend-api/codex",
        "apiKey": "换成你的key",
        "api": "openai-responses",
        "models": [
          {
            "id": "gpt-5.2",
            "name": "GPT-5.2"
          },
          {
            "id": "gpt-5.2-codex",
            "name": "GPT-5.2 Codex"
          }
        ]
      },
      "aicodemirror-gemini": {
        "baseUrl": "https://api.aicodemirror.com/api/gemini/v1",
        "apiKey": "换成你的key",
        "api": "openai-completions",
        "models": [
          {
            "id": "gemini-3-pro-preview",
            "name": "Gemini 3 Pro Preview"
          },
          {
            "id": "gemini-3-flash-preview",
            "name": "Gemini 3 Flash Preview"
          }
        ]
      }
    }
  }
}
```

## 四、重启网关并验证

- MacOS/Linux：

```bash
openclaw gateway restart
```

- Windows：

```powershell
openclaw gateway
```

在网关网页 `chat` 中依次执行：

```text
/models
/models aicodemirror-claude
/model aicodemirror-claude/claude-opus-4-5-20251101
你好
```

如模型正常回复，即配置成功。

## 五、Telegram 对话（可选）

1. 在 Telegram 里找 `BotFather`，执行 `/newbot` 获取 Bot Token。
2. 在本地网关页面 `Config -> Channels -> Telegram Bot Token` 填入 Token。
3. 配置本地代理（示例：`http://127.0.0.1:7890`）。
4. 获取 Pairing code 后执行：

```bash
openclaw pairing approve telegram 你的配对code
```

5. 回到 Telegram 与机器人对话，测试是否成功。

---

如果你还没有 AICodeMirror 账号，可通过下方邀请链接注册：

https://www.aicodemirror.com/register?invitecode=EZUWFL
