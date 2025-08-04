# Whatsapp-Bridge-Telegram-JS-Multi

A bridge between WhatsApp and Telegram that allows you to manage WhatsApp conversations through Telegram. Multi account version.

## Screnshoot
| Login WA 1 | Login WA 2 | Try Chat | Chat on Topic | Whatsapp |
|---|---|---|---|---|
| <img src="https://raw.githubusercontent.com/brianandhikap/WhatsTelBridgeJS-Multi/refs/heads/main/img/1.png" width="500"/> | <img src="https://raw.githubusercontent.com/brianandhikap/WhatsTelBridgeJS-Multi/refs/heads/main/img/2.png" width="500"/> | <img src="https://raw.githubusercontent.com/brianandhikap/WhatsTelBridgeJS-Multi/refs/heads/main/img/3.png" width="500"/> | <img src="https://raw.githubusercontent.com/brianandhikap/WhatsTelBridgeJS-Multi/refs/heads/main/img/4.png" width="500"/> |  <img src="https://raw.githubusercontent.com/brianandhikap/WhatsTelBridgeJS-Multi/refs/heads/main/img/5.png" width="500"/> |

## 🆕 Features

- Multi-Session Support
- Bridge WhatsApp messages to Telegram and vice versa
- Organize conversations in Telegram topics
- Support for text, images, videos, and audio messages
- Special handling for WhatsApp stories
- User management with initials for message attribution
- Command system for managing chats and users
- Message Reactions
- Improved Database Schema

## 🔧 Requirements

- Node.js 16+
- MySQL database
- Telegram Bot Token
- Two Telegram groups (one for topics, one for general messages)

## 🔧 Setup

1. Clone the repository
   ```bash
   git clone https://github.com/brianandhikap/WhatsTelBridgeJS-Multi
   
2. Install dependencies: `npm install`
3. Create a `.env` file with the following variables:

```
TELEGRAM_BOT_TOKEN=your_telegram_bot_token
TELEGRAM_TOPIC_GROUP=your_topic_group_id
TELEGRAM_FULL_GROUP=your_general_group_id
SUPERADMINS=ID_Tele_Admin_1,ID_Tele_Admin_2

MYSQL_HOST=your_mysql_host
MYSQL_USER=your_mysql_user
MYSQL_PASSWORD=your_mysql_password
MYSQL_DATABASE=your_mysql_database
```

4. Start the application: `npm start`

## Commands

- `!chat [session_name]-[phone_number] [message]` - Start or continue a chat with a WhatsApp user
- `!close` - Close a topic (use in topic only)
- `!add_user [telegram_id] [initial]` - Add a user (superadmin only)
- `!rm_user [telegram_id]` - Remove a user (superadmin only)
- `!help` - Show help message

## Telegram Groups Setup

1. Create two Telegram groups:
   - One for topics (must have topics enabled)
   - One for general messages
2. Add your bot to both groups with admin privileges
3. Get the group IDs and add them to your `.env` file

## User Management

Only authorized users can send messages. Superadmins can add users with the `!add_user` command.
Each user has an initial that is appended to their messages for attribution.

# 📝 **Commands:**

## 📱 **Session Management:**

- `!login <session_name>` - Create new WhatsApp session (superadmin only)
- `!sessions` - List all sessions with their status


## **Chat Commands:**

- `!chat [session_name]-[phone_number] [message]` - Start or continue chat
- `!close` - Close topic (use in topic only)


## **Admin Commands:**

- `!add_user [telegram_id] [initial]` - Add user
- `!rm_user [telegram_id]` - Remove user
- `!check_admin` - Check superadmin status
- `!set_group full/topic` - Set current chat as group
- `!help` - Show help message
- `!get_groups [session_name]` - Get groups ID by session name
- `!forward_groups [session_name]-[ID_Groups]` - Start forwardi from groups
- `!disforward_groups [nama_session]-[ID_Groups]` - Stop forward chat from groups


## 🚀 **Usage Examples:**

```
!login Helpdesk-01
!login CustomerService-02
!login Support-Team
!sessions
!chat Helpdesk-01-628123456789 Hello, how can I help you?
```
