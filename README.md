# 🎮 FreezeHost 自动续期

使用 Playwright + GitHub Actions 每天自动续期 FreezeHost 免费服务器。

## ⚙️ 配置步骤

### 1️⃣ Fork 或上传此仓库到 GitHub

### 2️⃣ 添加 Secrets

进入仓库 → **Settings** → **Secrets and variables** → **Actions** → **New repository secret**：

| 🔑 Secret 名称 | 📝 格式 | ✅ 必填 |
|---|---|---|
| `DISCORD_ACCOUNT` | `email,password` | ✅ |
| `TG_BOT` | `chat_id,bot_token` | ✅ |
| `GOST_PROXY` | `socks5://host:port` | 可选 |

### 3️⃣ 启用 Actions

进入 **Actions** 标签页，点击 **Enable GitHub Actions**。

### 4️⃣ 手动触发测试

**Actions** → **🎮 FreezeHost 自动续期** → **Run workflow**

## 🕐 运行时间

每天 **UTC 08:00**（北京时间 16:00）自动运行。
可在 `.github/workflows/freeze.yml` 的 `cron` 表达式中修改。

## 📊 续期结果说明

| 状态 | 说明 |
|---|---|
| ✅ passed | 续期成功，TG 已推送通知 |
| ⚠️ skipped | 余额不足，待赚够金币后下次自动重试 |
| ❌ failed | 登录失败或脚本异常，查看 failure-screenshots |
