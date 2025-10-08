# 📊 Daily GitHub Repo Report Workflow

This repository contains a GitHub Actions workflow that generates a daily report of issues from one or more repositories (including private repos in your organization) and sends it to a Microsoft Teams channel. 🚀

---

## 🛠️ Setup Instructions

### 1️⃣ Generate a Fine-Grained Personal Access Token (PAT)

To access **private repositories** and fetch issues information, you need a Fine-Grained PAT with the minimum required permissions.

**Steps:**

1. Go to your GitHub profile → **Settings** → **Developer settings** → **Personal access tokens** → **Tokens (fine-grained)** → **Generate new token**. 🔑
2. Select your **Organization** as the resource owner. 🏢
3. Choose **Specific repositories** or **All repositories** in your organization that the token should access. 📂
4. Grant the following repository permissions **(Read-only)**:  
   - **Issues** — Read-only (to fetch issues and comments) 🐞  
   - **Metadata** — Read-only (to fetch repo info and URLs) 🗂️  
5. (Optional) Add **Pull requests** read-only if you want PR info. 🔄  
6. Set an expiration date for the token as per your organization's policy. ⏳  
7. Generate the token and **copy it immediately**. ⚠️

---

2️⃣ Microsoft Teams Webhook Setup

To send the report to Microsoft Teams:

In Teams, go to the channel where you want to receive the report. 💬

Click the ... (More options) next to the channel name → Connectors. 🔌

Search for Incoming Webhook, and add it. ➕

Give it a name and upload an optional icon. 🏷️

Copy the Webhook URL provided. 🔗

Add this URL as the TEAMS_WEBHOOK_URL secret in your GitHub repository. 🔐

_______

### 3️⃣ Add Secrets to Your GitHub Repository

Go to your repository → **Settings** → **Secrets and variables** → **Actions** → **New repository secret**. 🔐

Add the following secrets:

| Secret Name         | Description                                |
|---------------------|--------------------------------------------|
| `PAT_TOKEN`         | Your Fine-Grained Personal Access Token.  🔑 |
| `TEAMS_WEBHOOK_URL` | Your Microsoft Teams Incoming Webhook URL. 📲 |

---

📝 Summary
Step	Description
🔑 Fine-Grained PAT	Token with repo access (Issues & Metadata Read-only)
🔒 GitHub Secrets	Store PAT_TOKEN and TEAMS_WEBHOOK_URL securely
⚙️ Workflow Env Vars	Use secrets in env section of your workflow YAML
📲 Teams Webhook	Incoming Webhook URL to post daily reports

🙏 Thank you for using this workflow!
For any issues or improvements, feel free to create an issue in this repo. 🐞

<img width="987" height="817" alt="Screenshot 2025-08-11 163146" src="https://github.com/user-attachments/assets/9a553f3f-8146-4e84-b39e-fbb5b41860d5" />

