# 🎉 Birthday Notifier Bot

A lightweight **Telegram bot** built using **Telethon**, designed to send daily birthday reminders directly to your Telegram chat. Never forget a loved one's special day again!


## Choose the correct branch

   - **For the Telethon MTProto version**: Use the `master` branch.
   - **For the Bot API version**: Switch to the `main` branch.

---

## ✨ Features  
- **Customizable Birthday List**: Manage birthdays in the `birthdays.json` file.  
- **Daily Notifications**: Automatically checks and sends reminders at a specific time.  
- **Age Calculation**: Automatically includes the recipient's age if the birth year is provided.  
- **Error Handling**: Graceful error messages for missing files, invalid JSON, or Telegram issues.  

---

## 🚀 How It Works  
1. The bot reads the `birthdays.json` file for upcoming birthdays.  
2. If a match is found, it formats a message and sends it to your Telegram chat.  
3. Runs daily using a scheduler (e.g., GitHub Actions, Cron jobs).  

---

## 🚀 GitHub Actions Workflow for Birthday Notifier Bot

This section will guide you on setting up a scheduled cron job using **GitHub Actions** to run the Birthday Notifier bot automatically every day.

### 🛠️ Workflow Setup

The GitHub Actions workflow runs the bot daily at **10:00 PM UTC** to check for birthdays and send notifications. The job is defined in the `.github/workflows/birthday_notifier.yml` file.

### 📅 Scheduled Trigger

The bot is set to run daily at a specific time using the `cron` syntax:
```yaml
on:
  schedule:
    - cron: '0 22 * * *' # Runs daily at 10:00 PM UTC
```
You can modify the cron expression if you need the bot to run at a different time.

### 🔄 Manual Trigger

You can also manually trigger the workflow via GitHub's Workflow Dispatch option:
```
on:
  workflow_dispatch:  # Allows manual triggering of the workflow
```

## 🧑‍💻 Workflow Steps

1. **Checkout the code**

   Ensure you have a directory `.github/workflows/` in your repository. Inside this directory, create or modify the file `bot.yml` (change it from `bot dot yml` to `bot.yml`).

2. **Set up environment variables**

   Before running the workflow, make sure to add the following environment variables to your GitHub repository's **Settings > Secrets**. These variables are used to securely store sensitive information like your Telegram bot credentials.

### Example Environment Variables:

   - `TELEGRAM_BOT_TOKEN`: Your Telegram bot token.
   - `TELEGRAM_CHAT_ID`: The chat ID where the notifications will be sent (either personal or group chat).

   You can add these secrets by navigating to **Settings > Secrets > New repository secret**.

Now, your bot will automatically check for birthdays and notify you every day at the set time! 🎉

---

## 🛠️ Installation Locally or VPS

1. **Clone the Repository**  
   ```bash
   git clone https://github.com/ankit-chaubey/birthday-notifier.git
   cd birthday-notifier
   ```

### 2. Set Up Environment Variables

Define these in your system or a .env file:
```
TELEGRAM_BOT_TOKEN – Your Telegram bot token.

TELEGRAM_CHAT_ID – Chat ID to receive notifications.
```
---

## 3. Install Dependencies

```
pip install -r requirements.txt
```

## 4. Run the Script

```
python birthday_notifier.py
```

---

### 🗂️ File Structure

```
.
├── birthdays.json          # JSON file storing birthday data
├── birthday_notifier.py    # Main script for notifications
├── requirements.txt        # Python dependencies
└── README.md               # Documentation
```

---

### 📅 Example birthdays.json

```
[
  { "name": "Ankit", "date": "2002-06-12" },
  { "name": "John", "date": "1998-03-15" },
  { "name": "Alice", "date": "2000-11-24" }
]
```

---

## 🤝 Contributing

Feel free to open issues or submit pull requests. Let’s make this bot even better together!

---

## 📜 License

This project is licensed under the MIT [License](License).

---

Start celebrating birthdays like a pro! 🎂
