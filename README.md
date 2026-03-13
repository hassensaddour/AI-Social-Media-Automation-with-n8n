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

<img width="1525" height="623" alt="Capture d&#39;écran 2026-03-13 022035" src="https://github.com/user-attachments/assets/8e041eeb-8b1c-4eaa-ab03-6f55a4225f13" />


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

# 🔑 Required Credentials

Before running the workflow, configure these credentials inside n8n:

* Notion API
* Telegram Bot Token
* Google Drive API
* LinkedIn API
* Facebook Graph API
* Gemini AI API

---

# 🗂 Notion Database Structure

The Notion database acts as the **content management system**.

<img width="1069" height="810" alt="Capture d&#39;écran 2026-03-12 073234" src="https://github.com/user-attachments/assets/899b19f2-30cf-444f-a0f9-b12da0b3eb36" />


Once a post is published, its status is updated to **Published** to prevent duplicates.

---

# 📬 Telegram Approval System

The workflow sends the generated content to Telegram.

<img width="518" height="517" alt="Capture d&#39;écran 2026-03-12 072919" src="https://github.com/user-attachments/assets/35f083b9-a252-4658-8e5f-f32368ad985b" />


---

# 📢 Social Media Publishing

If approved, the workflow automatically publishes the post to:

### LinkedIn

<img width="727" height="844" alt="Capture d&#39;écran 2026-03-12 073044" src="https://github.com/user-attachments/assets/67a4913c-b56e-474c-9951-7d98f37c8d2a" />


### Facebook

Publishes the post to a configured Facebook Page using the Facebook Graph API.
<img width="803" height="753" alt="Capture d&#39;écran 2026-03-12 073103" src="https://github.com/user-attachments/assets/b71fc327-496d-46db-86e8-6615eba532f7" />


---

# 📩 Notification After Publishing

After successful publication, the user receives a Telegram message:

<img width="640" height="357" alt="Capture d&#39;écran 2026-03-12 073153" src="https://github.com/user-attachments/assets/d7b3a630-38f9-4b1b-9d59-3043676b6786" />

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
