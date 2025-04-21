# telegram-bot-broadcast-website
free telegram bot broadcast 
Here’s a professional, clear, and user-friendly README template for your Telegram Bot Broadcast platform, tailored to your website and API documentation.

---

# Telegram Bot Broadcast Platform

Easily manage and broadcast messages to your Telegram bot subscribers without coding.

## 🌐 Website

[https://broadcast.findolucky.site](https://broadcast.findolucky.site)

---

## 🚀 Features

- **Broadcast messages** to all users of your Telegram bot
- **No coding required** – simple web interface
- **Register multiple bots** and manage them from one dashboard
- **Export subscriber user IDs**
- **API access** for advanced integrations

---


## 📝 Getting Started

### 1. Register Your Telegram Bot

1. **Create a Telegram bot** using [@BotFather](https://core.telegram.org/bots#botfather) on Telegram ([How to create a bot?][5]).
2. Copy your bot’s token from BotFather.

### 2. Add Your Bot to the Platform

1. Go to [broadcast.findolucky.site](https://broadcast.findolucky.site).
2. Sign up or log in.
3. Register your bot by pasting your Telegram bot token.

### 3. Set Up Webhook

- After registering your bot, click “Setup Webhook” in your bot’s dashboard.
- This connects your bot to the platform for message broadcasting.

### 4. Start Broadcasting

- Use the web dashboard to send messages to all your bot subscribers.
- You can also export user IDs of your subscribers.

---

## 📖 API Documentation

- Full API documentation is available at  
  [https://broadcast.findolucky.site/api_doc.php?bot_id=YOUR_BOT_ID](https://broadcast.findolucky.site/api_doc.php?bot_id=YOUR_BOT_ID)

Replace `YOUR_BOT_ID` with your actual bot ID.

---

## 📦 Example API Usage

```import requests
from telegram import Update
from telegram.ext import ApplicationBuilder, CommandHandler, ContextTypes

API_URL = "https://broadcast.findolucky.site/api.php"
BOT_TOKEN = "YOUR_BOT_TOKEN"  # The token you registered on your site

async def start(update: Update, context: ContextTypes.DEFAULT_TYPE):
    user = update.effective_user

    params = {
        "token": BOT_TOKEN,
        "user": user.id,
        "first_name": user.first_name or "",
        "last_name": user.last_name or "",
        "username": user.username or ""
    }

    # Send the data to your API
    try:
        response = requests.get(API_URL, params=params, timeout=5)
        print("API response:", response.text)
    except Exception as e:
        print("Error calling API:", e)

    await update.message.reply_text("Welcome! You have been registered.")

if __name__ == "__main__":
    app = ApplicationBuilder().token("YOUR_TELEGRAM_BOT_TOKEN").build()
    app.add_handler(CommandHandler("start", start))
    app.run_polling()
```

See the [API documentation](https://broadcast.findolucky.site/api_doc.php) for all available endpoints and parameters.

---

## ❓ FAQ

**Q: Do I need to host my own server?**  
A: No, everything runs on [broadcast.findolucky.site](https://broadcast.findolucky.site).

**Q: Is my bot token safe?**  
A: Your bot token is stored securely and used only to send messages you authorize.

**Q: Can I export my subscribers?**  
A: Yes, you can export user IDs in CSV, JSON, or TXT format directly from your dashboard.

---

## 🤝 Contributing

Pull requests are welcome! For major changes, please open an issue first to discuss what you would like to change.

---

## 📄 License

This project is licensed under the MIT License.

---

## 📬 Contact

For support or questions, contact [telegram group](https://t.me/globalhelper) support.
For support or questions, contact [admin](https://t.me/forwardtarbot)  direct support.

---


