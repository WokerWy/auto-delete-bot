# 🤖 Auto Delete Telegram Bot

A powerful Telegram bot to automatically delete group messages after a set time. Admins can control the deletion timer.

---

## 🔧 Features

- 🕒 Auto-delete group messages after N seconds
- 🔐 Admin-only controls: `/set_time`, `/disable`, `/status`
- 🔊 Broadcast to all users via `/broadcast`
- 👤 Get total user count via `/users`
- 📌 Force channel join (admin-only restriction)
- 🎛 Inline menu: `/start`, Help, About with Back button
- 💾 MongoDB-based settings and user storage
- 🌐 Flask keep-alive server for Replit/Render deployment

---

## 📁 Project Structure

```
Tele-Auto-Delete-Bot/
├── bot.py           # Bot logic
├── config.py         # Config from env variables
├── requirements.txt  # Python dependencies
└── README.md         # You're reading it!
```

---

## ⚙️ Configuration

### 🔐 Environment Variables

Create a `config.py` file or set these variables in your hosting environment:

```env
API_ID=your_telegram_api_id
API_HASH=your_telegram_api_hash
BOT_TOKEN=your_bot_token
DATABASE_URL=your_mongodb_connection_uri
BOT_USERNAME=Auto_Deleter_1Bot      # Without @
FORCE_SUB_CHANNEL=kissubots         # Without @
OWNER_ID=123456789                  # Your Telegram user ID
PORT=8080                           # Optional (for Flask)
```

---

## 🚀 Deployment

### ▶️ Local Setup

1. Install Python dependencies:
   ```bash
   pip install -r requirements.txt
   ```

2. Run the bot:
   ```bash
   python3 bot.py
   ```

> ✅ MongoDB must be accessible and populated with collections automatically.

---

### ☁️ Cloud Deployment (Replit / Render / Railway)

- Upload all files
- Set environment variables in the dashboard
- Ensure `PORT` is available if using Flask (Replit/Render)
- Run `bot.py`

---

## 📚 Commands Reference

### 👥 Group Commands (Admins Only)

| Command          | Description                              |
|------------------|------------------------------------------|
| `/set_time 10`   | Set delete timer to 10 seconds           |
| `/disable`       | Disable auto-delete in the group         |
| `/status`        | Show current delete timer for the group  |

---

### 🧑‍💻 Owner Commands (Private Only)

| Command                | Description                          |
|------------------------|--------------------------------------|
| `/broadcast <message>` | Broadcast a message to all users     |
| `/users`               | View total registered users          |

---

### 🔘 Callback Button Features

- Help: Shows usage of commands
- About: Bot info and credits
- Back: Returns to start menu

---

## 🔒 Force Subscription

Only group admins are forced to join the specified channel before using the bot.

Set the channel username in `.env`:
```
FORCE_SUB_CHANNEL=your_channel_username
```

---

## 📌 Notes

- Messages from group admins and bots are never deleted.
- Only group admins can configure delete time.
- Only bot owner can use `/broadcast` and `/users`.

---
