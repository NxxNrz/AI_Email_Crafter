# 🧾 AI Email Crafter: VC Outreach Auto-Draft Assistant

An AI-powered Streamlit app that generates personalized outreach emails to VCs and saves them directly into your Gmail Drafts using OpenRouter + Gmail API.

---

## 🧠 Features

- 📤 Upload list of VC names, firms, and investment focus (CSV/XLSX)
- 🤖 Automatically generate subject & body using `mistralai/mistral-7b-instruct` via [OpenRouter](https://openrouter.ai/)
- 🔎 Edit and preview the generated emails in-app
- 💾 Save each email to your Gmail drafts with one click using Gmail API
- 🔐 Secure API keys via `.streamlit/secrets.toml`

---

## 📂 Project Structure

```bash
AI_EMAIL_CRAFTER/
├── app.py                      # Main Streamlit app
├── credentials.json            # OAuth client for Gmail API (add this manually)
├── requirements.txt            # All required Python packages
├── token.pickle                # Stores Gmail OAuth token after login
├── README.md                   # This file
├── .streamlit/
│   └── secrets.toml            # OpenRouter API key
├── templates/                  # (optional) For future templating
├── assets/                     # (optional) For images/screenshots
└── utils/
    ├── __init__.py
    ├── email_generator.py      # LLM integration with OpenRouter
    ├── gmail_api.py            # Gmail draft saver via Gmail API
```

---

## 🛠️ Setup

### 1. Clone the repo and install dependencies

```bash
pip install -r requirements.txt
```

### 2. Create `.streamlit/secrets.toml`:

```toml
[openrouter]
api_key = "sk-xxxxxxxxxxxxxxxx"
```

### 3. Add Gmail credentials

Go to [Google Cloud Console](https://console.cloud.google.com/):
- Enable Gmail API
- Create OAuth 2.0 client (Desktop App)
- Download `credentials.json` and place it in the project root

---

## 🚀 Run the App

```bash
streamlit run app.py
```

---

## 📊 Sample Input

Upload a file like:

```csv
Name,Firm,Focus
Alice Zhang,Hustle Fund,AI and SaaS
Brian Lee,Goodwater Capital,Consumer Tech
```

---

## 🔐 Gmail OAuth

- On first use, app will prompt you to sign in with Google
- A `token.pickle` file is created to store your credentials
- Emails are saved as drafts — no messages are sent without your approval

---

## 🧪 Example Email Output

| VC Name     | Firm            | Subject                             | Body                |
|-------------|------------------|--------------------------------------|----------------------|
| Alice Zhang | Hustle Fund      | Satu Energy: AI-Powered Innovation   | Dear Alice...        |

You can expand and edit before saving to Gmail drafts.

---

## 🔧 Tech Stack

- Streamlit
- OpenRouter + Mistral 7B
- Gmail API (OAuth)
- Pandas
- Python 3.10+

---

## 📌 Tags

streamlit ai-email gmail-api openrouter llm cold-email personalization google-auth mistral7b email-drafts outreach automation vc-tools

---

## 🧠 Use Cases

- VC Outreach for startup fundraising
- Cold emailing with AI personalization
- BD/Sales email generation at scale
- Save time on repetitive drafting

---
