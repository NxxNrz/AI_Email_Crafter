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
![{F0F6606E-98E3-4708-B167-18425FA1905E}](https://github.com/user-attachments/assets/1d983189-709a-433f-8772-f2d8f39d79dc)
![{C313E1C3-0F59-44FF-9B8E-3FC2DF3E4BE5}](https://github.com/user-attachments/assets/80e59fc2-5162-4db1-b78b-6fda3da576aa)
![{FADC5F00-F1B1-4CDE-9BE1-7B8B48CBD5EA}](https://github.com/user-attachments/assets/67d46941-048d-451d-8641-d559056a305c)
![{BEC6F926-4633-425B-9518-BE2C357D473B}](https://github.com/user-attachments/assets/0a4c6f87-7cc5-4188-a2b7-1c071807a6e0)
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
