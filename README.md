# 🤖 Jarvis AI — Voice-Enabled Personal Assistant (n8n + Gemini)

An autonomous, conversational AI agent ("Jarvis") constructed on **n8n** and powered by **Google Gemini 2.5 Flash**. Jarvis accepts real-time voice and text inputs, manages context across turns, and dynamically executes actions across **Google Calendar** and **Gmail**.

---

## 📌 Features

- **🎙️ Voice-To-Text Interface:** Directly record voice commands inside the n8n Chat Trigger interface.
- **🧠 State & Context Memory:** Maintains multi-turn conversation memory using a Window Buffer Memory node.
- **📅 Google Calendar Integration:** Fetch events, create meetings, check availability, and manage schedules via natural language.
- **📧 Gmail Automation:** Draft, read, filter, and send emails hands-free.
- **⚡ Gemini 2.5 Flash Powered:** High-speed, low-latency function calling and decision routing.

---

## 🛠️ Prerequisites

Before getting started, make sure you have:

1. An active **n8n instance** (Self-hosted or n8n Cloud).
2. A **Google Account** (for Google Calendar and Gmail access).
3. A **Google AI Studio API Key** (for Gemini 2.5 model access).

---

## 🔑 Step-by-Step Credentials Setup

### 1. Google Gemini API Key
1. Go to [Google AI Studio](https://aistudio.google.com/).
2. Log in with your Google account and click **Get API Key**.
3. Click **Create API Key** and copy the generated key string.
4. In n8n, double-click the **Google Gemini Chat Model** node.
5. Under **Credential for Google Gemini API**, click **Create New Credential**, paste your API key, and click **Save**.

---

### 2. Google OAuth2 Setup (Google Calendar & Gmail)
To grant Jarvis access to read and write to your Calendar and Gmail:

1. Go to the [Google Cloud Console](https://console.cloud.google.com/).
2. Create a new project (e.g., `n8n-Jarvis-Assistant`).
3. In the sidebar, navigate to **APIs & Services > Library**.
4. Search for and **Enable** the following APIs:
   - **Google Calendar API**
   - **Gmail API**
5. Go to **APIs & Services > OAuth Consent Screen**:
   - Select **External** and click **Create**.
   - Fill in the App Name (`Jarvis Assistant`) and user support email.
   - Add your own email address under **Test Users** (crucial for development mode).
6. Go to **APIs & Services > Credentials**:
   - Click **Create Credentials > OAuth Client ID**.
   - Set **Application Type** to **Web Application**.
   - Under **Authorized Redirect URIs**, copy and paste the Redirect URI provided inside your n8n Google OAuth credential screen (e.g., `https://your-n8n-instance.com/rest/oauth2-credential/callback`).
7. Copy your **Client ID** and **Client Secret**.
8. In n8n, create new OAuth2 credentials for the **Google Calendar Tool** and **Gmail Tool** nodes using these client values, then complete the Google sign-in consent flow.

---

## 🚀 Installation & Deployment

1. Clone this repository:
   ```bash
   git clone [https://github.com/](https://github.com/)<YOUR_GITHUB_USERNAME>/jarvis-n8n-voice-assistant.git
   cd jarvis-n8n-voice-assistant

<img width="1157" height="562" alt="Screenshot 2026-10-01 004700" src="https://github.com/user-attachments/assets/b6543928-2058-4b19-b6ef-dc8a30de3f0c" />
   
   
