<div align="center">

<!-- Animated Banner -->
<img src="banner.png" alt="FCA-Anurag Miishraa Banner" width="100%" style="border-radius: 15px; box-shadow: 0 10px 30px rgba(0,123,255,0.3);">

<!-- Animated Title -->
<h1>
  <img src="https://readme-typing-svg.herokuapp.com?font=Fira+Code&size=35&duration=3000&pause=1000&color=007BFF&center=true&vCenter=true&width=600&lines=🚀+FCA-Anurag+Miishraa;Facebook+Chat+API;Production+Ready;Bug+Fixed+Fork" alt="Typing Animation">
</h1>

<!-- Animated Badges -->
<p>
  <img src="https://img.shields.io/npm/v/fca-anurag-miishraa.svg?style=for-the-badge&logo=npm&logoColor=white&color=CB3837" alt="npm version">
  <img src="https://img.shields.io/npm/dm/fca-anurag-miishraa.svg?style=for-the-badge&logo=npm&logoColor=white&color=007BFF" alt="npm downloads">
  <img src="https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge&logo=opensourceinitiative&logoColor=white" alt="License">
  <img src="https://img.shields.io/node/v/fca-anurag-miishraa.svg?style=for-the-badge&logo=node.js&logoColor=white&color=339933" alt="Node.js">
</p>

<!-- Animated Divider -->
<img src="https://user-images.githubusercontent.com/73097560/115834477-dbab4500-a447-11eb-908a-139a6edaec5c.gif" width="100%">

</div>

<!-- Animated Introduction -->
<div align="center">

### ✨ **Made with ❤️ by ANURAG MISHRA** ✨

<p align="center">
  <img src="https://readme-typing-svg.herokuapp.com?font=Fira+Code&size=18&duration=2000&pause=500&color=00D4AA&center=true&vCenter=true&width=800&lines=💬+Real-time+Facebook+Messenger+API;🔧+Bug+Fixed+%26+Production+Ready;🚀+Advanced+Features+%26+Stability;🎨+AI+Theme+Generation;⚡+Fast+%26+Reliable" alt="Features Animation">
</p>

</div>

---

## 🎯 What's Special About This Fork?

<div align="center">

<table>
<tr>
<td width="50%">

### ❌ Before (Original)
```
🔴 Memory Leaks
🔴 Infinite Reconnect Loops
🔴 CPU Hogging
🔴 Random Crashes
🔴 Resource Waste
```

</td>
<td width="50%">

### ✅ After (This Fork)
```
🟢 Memory Optimized
🟢 Smart Reconnect
🟢 CPU Efficient
🟢 Stable & Reliable
🟢 Production Ready
```

</td>
</tr>
</table>

</div>

---

## 🔧 Bug Fixes & Improvements

| Issue | Status | Description |
|-------|--------|-------------|
| 🐛 Memory Leak | ✅ **FIXED** | Old MQTT clients properly cleaned up |
| 🔄 Hot Reconnect Loop | ✅ **FIXED** | No more infinite loops |
| 💾 Resource Management | ✅ **FIXED** | All resources properly released |
| 🚫 Retry Limits | ✅ **ADDED** | Max 50 reconnects, 10 getSeqID failures |
| ⚠️ Promise Rejections | ✅ **FIXED** | Safe promise handling |
| 🏭 Production Ready | ✅ **YES** | Graceful stop notifications |

---

## 📦 Installation

```bash
# Using npm
npm install fca-anurag-miishraa

# Using yarn
yarn add fca-anurag-miishraa

# Latest version
npm install fca-anurag-miishraa@latest
```

> ⚠️ **Requirements:** Node.js v18.0.0 or higher

---

## 🚀 Quick Start

### 1️⃣ Setup AppState

Create `appstate.json` with your Facebook cookies:

```json
[
  { "key": "c_user", "value": "your-user-id" },
  { "key": "xs", "value": "your-xs-token" },
  { "key": "datr", "value": "your-datr-token" }
]
```

### 2️⃣ Basic Bot

```javascript
const { login } = require("fca-anurag-miishraa");

login({ appState: require("./appstate.json") }, (err, api) => {
  if (err) return console.error("❌ Login failed:", err);
  
  console.log("✅ Bot is running!");
  
  api.listenMqtt((err, message) => {
    if (err) return console.error(err);
    
    if (message.type === "message") {
      console.log(`💬 ${message.senderID}: ${message.body}`);
      
      api.sendMessage(`Echo: ${message.body}`, message.threadID);
    }
  });
});
```

### 3️⃣ Advanced Options

```javascript
const options = {
  selfListen: false,      // Don't listen to own messages
  listenEvents: true,     // Listen to events
  autoReconnect: true,    // Auto-reconnect
  autoMarkRead: true,     // Auto-mark as read
  online: true,           // Show as online
  emitReady: true         // Emit ready event
};

login({ appState: require("./appstate.json") }, options, (err, api) => {
  // Your code here
});
```

---

## 🎨 AI Theme Generation

```javascript
// Create custom AI theme
api.createAITheme({
  threadID: "your-thread-id",
  themePrompt: "ocean sunset with purple gradients",
  callback: (err, result) => {
    if (!err) console.log("🎨 Theme created!", result);
  }
});
```

---

## 📚 API Methods

### 💬 Messaging
- `sendMessage(message, threadID, callback)` - Send messages
- `sendTypingIndicator(threadID, callback)` - Typing indicator
- `markAsRead(threadID, callback)` - Mark as read
- `editMessage(text, messageID, callback)` - Edit messages

### 👥 Thread Management
- `getThreadInfo(threadID, callback)` - Thread info
- `getThreadHistory(threadID, amount, timestamp, callback)` - Message history
- `getThreadList(limit, timestamp, tags, callback)` - Thread list
- `changeThreadColor(color, threadID, callback)` - Change color

### 👤 User Info
- `getUserInfo(ids, callback)` - User information
- `getUserID(name, callback)` - Get user ID
- `getFriendsList(callback)` - Friends list

---

## ⚙️ Configuration Options

| Option | Type | Default | Description |
|--------|------|---------|-------------|
| `selfListen` | boolean | false | Listen to own messages |
| `listenEvents` | boolean | true | Listen to events |
| `autoReconnect` | boolean | true | Auto-reconnect |
| `autoMarkRead` | boolean | true | Auto-mark read |
| `online` | boolean | true | Show as online |
| `emitReady` | boolean | false | Emit ready event |
| `userAgent` | string | default | Custom user agent |
| `proxy` | string | null | Proxy URL |

---

## 🔒 Security Warning

> ⚠️ **IMPORTANT:** `appstate.json` contains sensitive credentials!

- ❌ Never commit to version control
- ❌ Never share publicly
- ✅ Add to `.gitignore`
- ✅ Treat like a password

---

## 🐛 Troubleshooting

<details>
<summary><b>Bot Not Receiving Messages</b></summary>

- ✅ Verify `appstate.json` is valid
- ✅ Check Facebook login in browser
- ✅ Ensure account isn't restricted
</details>

<details>
<summary><b>Login Errors</b></summary>

- 🔄 Re-export cookies
- 🧹 Clear Facebook cookies
- 🌐 Try different browser
</details>

<details>
<summary><b>Connection Issues</b></summary>

- 🔌 Check network connection
- ⏱️ Bot auto-reconnects (max 50 times)
- 🔑 May need fresh session
</details>

---

## 📊 Stats

<div align="center">

![GitHub stars](https://img.shields.io/github/stars/anumishra22/Anurag-Miishraa-FCA-?style=social)
![GitHub forks](https://img.shields.io/github/forks/anumishra22/Anurag-Miishraa-FCA-?style=social)
![GitHub issues](https://img.shields.io/github/issues/anumishra22/Anurag-Miishraa-FCA-?style=social)

</div>

---

## 🙏 Credits

- Original `fca-anurag-miishraa` by **Anurag Miishraa**
- Bug fixes & improvements by **ANURAG MISHRA**
- Inspired by `ws3-fca` community

---

## 🔗 Links

<div align="center">

[![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/anumishra22/Anurag-Miishraa-FCA-.git)
[![npm](https://img.shields.io/badge/npm-CB3837?style=for-the-badge&logo=npm&logoColor=white)](https://www.npmjs.com/package/fca-anurag-miishraa)

</div>

---

<div align="center">

### ⭐ Star this repo if you find it helpful! ⭐

<img src="https://readme-typing-svg.herokuapp.com?font=Fira+Code&size=16&duration=3000&pause=1000&color=FF6B6B&center=true&vCenter=true&width=400&lines=Made+with+❤️+by+ANURAG+MISHRA;Happy+Coding!+🚀" alt="Footer Animation">

</div>

---

<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&height=100&section=footer&text=Thanks%20for%20visiting!&fontSize=20&fontAlignY=80">
</p>
