# ass-vibecoded-chat-thing
everything is made by ai not me 
HOW DO I UPLOAD MY 108MB ZIP FILE

heres very human typed code below explaiuning shit and im the best larp

# 💬 Chat Overlay — LAN/VPN Chat App

A lightweight, always-on-top Roblox-style chat overlay for LAN or VPN play sessions (Radmin, Tailscale, etc).

---

## 📁 Project Structure

```
chat-overlay/
├── server/          ← Node.js Socket.IO server (run on host machine)
│   ├── server.js
│   └── package.json
└── client/          ← Electron desktop overlay (run on each player's machine)
    ├── package.json
    └── src/
        ├── main.js
        ├── preload.js
        └── index.html
```

---

## 🖥️ SERVER SETUP (Host Machine)

### Prerequisites
- Node.js v16+ installed

### Steps

```bash
cd server
npm install
npm start
```

The server will print:
```
🟢 Chat Overlay Server running on port 3000
   Listening on all interfaces (0.0.0.0:3000)
```

> **Firewall:** Make sure port **3000 TCP** is allowed through your firewall.
> - Windows: Windows Defender Firewall → Allow an app → add `node.exe`
> - Linux: `sudo ufw allow 3000/tcp`

### Finding Your IP

| Network | How to find IP |
|---------|---------------|
| LAN     | `ipconfig` (Windows) or `ip a` (Linux) — look for `192.168.x.x` |
| Radmin VPN | Open Radmin VPN → your IP shown in the network list (usually `26.x.x.x`) |
| Tailscale | `tailscale ip` in terminal (usually `100.x.x.x`) |

---

## 💻 CLIENT SETUP (Each Player)

### Prerequisites
- Node.js v16+ installed

### Steps

```bash
cd client
npm install
npm start
```

### First Launch
1. Enter your **Username** (max 20 chars)
2. Enter the **Host IP** (the server machine's LAN/VPN IP)
3. Enter a **Room Code** (e.g. `GAMENIGHT`, `SQUAD1`) — everyone in the same room must use the same code
4. Click **Connect**

---

## 🎮 Usage

| Action | How |
|--------|-----|
| Open chat input | Click the input bar OR press **`/`** |
| Send message | Press **Enter** or click **SEND** |
| Collapse window | Click **─** button in titlebar |
| Minimize to taskbar | Click **⊟** button |
| Close | Click **✕** button |

---

## ⚙️ Features

- ✅ Always-on-top overlay (stays above games)
- ✅ Semi-transparent dark UI
- ✅ Room-based chat (private per room code)
- ✅ Real-time Socket.IO messaging
- ✅ `/` key shortcut to focus chat
- ✅ Auto-reconnect on disconnect
- ✅ Online user count display
- ✅ System messages (join/leave/disconnect)
- ✅ Hover to reveal message timestamps
- ✅ Collapsible window

---

## 🔧 Troubleshooting

**"Cannot reach IP:3000"**
- Is the server running? (`npm start` in the `server/` folder)
- Is port 3000 open in the host's firewall?
- Are both machines on the same Radmin/Tailscale network?
- Try pinging the host IP first: `ping 192.168.x.x`
- im so ayyyyyy

**Messages not appearing**
- Make sure all users typed the same Room Code (case-insensitive, auto-uppercased)

**Window not staying on top**
- Some fullscreen exclusive games block always-on-top. Use Windowed or Borderless Windowed mode.
