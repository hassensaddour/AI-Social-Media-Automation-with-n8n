# AI-Social-Media-Automation-with-n8n
# 🤖 AI Social Media Automation with n8n

An automated social media content pipeline that generates posts using AI, requests human approval, and publishes them to multiple social media platforms.

This project demonstrates how to build a **fully automated AI-driven social media publishing system** using workflow automation.

The system retrieves topics from a content database, generates posts using AI, sends them for approval via Telegram, and automatically publishes them to LinkedIn and Facebook once approved.

---

# 🚀 Features

* 📅 Automated daily content pipeline
* 🤖 AI-generated social media posts
* 👤 Human approval workflow via Telegram
* 📢 Multi-platform publishing (LinkedIn + Facebook)
* 🖼 Automatic media retrieval from Google Drive
* 🗂 Content management using Notion
* 🔄 Status tracking to avoid duplicate posts
* 📬 Notification after successful publication

---

# 🧠 Workflow Overview

The automation runs every day at **12:00 PM** and follows this process:

1. **Schedule Trigger**
2. **Retrieve topics from Notion database**
3. **Generate post content using AI (Gemini)**
4. **Send generated post to Telegram for approval**
5. **User approves or rejects the content**
6. **If approved:**

   * Download media from Google Drive
   * Publish the post to LinkedIn
   * Publish the post to Facebook
7. **Send confirmation message to Telegram**
8. **Update the Notion database status to `Published`**

This ensures the same topic is not reused again.

---

# 🏗 Workflow Architecture

```
Schedule Trigger
      ↓
Get Topics from Notion
      ↓
Generate Post with AI
      ↓
Send to Telegram for Approval
      ↓
Approval Decision
   ↙        ↘
Reject      Approve
  ↓            ↓
Notify      Download Media
               ↓
        Publish to LinkedIn
               ↓
        Publish to Facebook
               ↓
       Send Telegram Notification
               ↓
     Update Notion Status (Published)
```

---

# 🛠 Technologies Used

| Tool               | Purpose                                 |
| ------------------ | --------------------------------------- |
| n8n                | Workflow automation                     |
| Notion             | Content database and editorial calendar |
| Telegram           | Approval system and notifications       |
| Gemini AI          | AI post generation                      |
| Google Drive       | Media storage                           |
| LinkedIn API       | Publish posts                           |
| Facebook Graph API | Publish posts                           |

---

# 📂 Repository Structure

```
ai-social-media-automation
│
├── workflow
│   └── n8n-workflow.json
│
├── images
│   └── workflow-diagram.png
│
├── README.md
└── LICENSE
```

---

# ⚙️ Installation

## 1️⃣ Install n8n

You can run n8n using Docker:

```bash
docker run -it --rm \
-p 5678:5678 \
-v ~/.n8n:/home/node/.n8n \
n8nio/n8n
```

Then open:

```
http://localhost:5678
```

---

# 🔑 Required Credentials

Before running the workflow, configure these credentials inside n8n:

* Notion API
* Telegram Bot Token
* Google Drive API
* LinkedIn API
* Facebook Graph API
* Gemini AI API

---

# 📥 Import the Workflow

1. Open n8n
2. Go to **Workflows**
3. Click **Import**
4. Upload:

```
workflow/n8n-workflow.json
```

---

# 🗂 Notion Database Structure

The Notion database acts as the **content management system**.

Example schema:

| Field       | Type        | Description                  |
| ----------- | ----------- | ---------------------------- |
| Topic       | Text        | Title of the post            |
| Description | Text        | Context for AI generation    |
| Media       | File / Link | Image stored in Google Drive |
| Status      | Select      | Todo / Published             |

Workflow logic:

```
Todo → Published
```

Once a post is published, its status is updated to **Published** to prevent duplicates.

---

# 📬 Telegram Approval System

The workflow sends the generated content to Telegram.

Example message:

```
📝 New Post Generated

Topic: AI in Cybersecurity

Generated Content:
[AI generated post text]

Approve this post?
```

User options:

* Approve
* Reject

---

# 📢 Social Media Publishing

If approved, the workflow automatically publishes the post to:

### LinkedIn

Supports:

* Personal profile
* Organization page

### Facebook

Publishes the post to a configured Facebook Page using the Facebook Graph API.

---

# 📩 Notification After Publishing

After successful publication, the user receives a Telegram message:

```
✅ Post Published Successfully

LinkedIn:
https://linkedin.com/...

Facebook:
https://facebook.com/...
```

---

# 🔐 Security Best Practices

Do not commit API keys or credentials to the repository.

Use environment variables:

```
.env
```

Example:

```
NOTION_API_KEY=
TELEGRAM_BOT_TOKEN=
LINKEDIN_ACCESS_TOKEN=
FACEBOOK_ACCESS_TOKEN=
```

---

# 🎯 Use Cases

This project can be used for:

* Personal brand automation
* Startup marketing
* AI-powered content pipelines
* Social media management automation
* Marketing agencies

---

# 🚀 Future Improvements

Possible enhancements:

* Instagram integration
* Twitter/X integration
* AI-generated images
* Hashtag optimization
* Analytics dashboard
* Multi-language post generation

---

# 👨‍💻 Author

Hassen Saddour

Cybersecurity Engineer & Automation Enthusiast

---

# ⭐ Support

If you find this project useful:

⭐ Star the repository
🍴 Fork it
🤝 Contribute improvements

---

# 📜 License

This project is licensed under the MIT License.
