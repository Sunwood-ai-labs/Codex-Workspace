<div align="center">

![Image](https://github.com/user-attachments/assets/04c68e93-e88b-45d2-bfab-8060c906dd7c)

# [Codex-Workspace](https://github.com/Sunwood-ai-labs/Codex-Workspace)

<p align="center">
  <img src="https://img.shields.io/badge/OpenAI_Codex-412991?style=for-the-badge&logo=openai&logoColor=white" alt="OpenAI Codex">
  <img src="https://img.shields.io/badge/GitHub_Actions-2088FF?style=for-the-badge&logo=github-actions&logoColor=white" alt="GitHub Actions">
  <img src="https://img.shields.io/badge/Automation-000000?style=for-the-badge&logo=robot&logoColor=white" alt="Automation">
</p>

<p align="center">
  A simple and efficient collection of GitHub Actions workflows leveraging OpenAI Codex
</p>

</div>

## 🚀 Overview

This repository is a lightweight set of workflows that harness the powerful capabilities of OpenAI Codex within GitHub Actions to automate repository tasks. By avoiding heavy processing and focusing on the essential features, it achieves both simplicity and efficiency.

## ✨ Features

- 💬 **Issue Auto-Response**: Codex analyzes new or updated issues and provides appropriate responses or fixes
- 📝 **Documentation Quality Check**: Automatically reviews the quality of README and other documentation and suggests improvements via pull request
- 🔍 **Code Review**: Automatically reviews pull request code and proposes enhancements
- 🌐 **README Translation**: Automatically translates README.md into Japanese and creates a pull request

## 📦 Setup

Follow the steps below to initialize the repository and configure the necessary environment variables and secrets.

### 1. Clone the repository

```bash
git clone https://github.com/<USERNAME>/<REPO>.git
cd <REPO>
```

### 2. Create the .env file

```bash
cp .env.example .env
```
Open the `.env` file and set the following environment variables:

* `OPENAI_API_KEY`    : OpenAI API key  
* `GITHUB_TOKEN`      : GitHub API token (optional; automatically provided in GitHub Actions)  
* `CODEX_QUIET_MODE`  : Codex quiet mode (e.g., `1`)  

### 3. Configure Secrets (for GitHub Actions)

In your repository, go to Settings > Secrets and add the following:

* `OPENAI_API_KEY` : OpenAI API key  

### 4. Enable Workflows

The workflows in `.github/workflows/` will be automatically enabled.

## 🛠️ Usage

### Issue Auto-Response

1. Create or update an issue
2. Codex analyzes the content and posts an appropriate response
3. If code fixes are needed, a pull request is created automatically

### Documentation Quality Check

1. Push changes to markdown files or open a pull request
2. Codex checks quality and auto-fixes suggested improvements
3. Proposes fixes in a pull request

### Code Review

1. Open a new pull request
2. Codex reviews the changes
3. Posts improvement suggestions as comments

### README Translation

1. Update `README.md`
2. Automatically create a Japanese version
3. Create a pull request with `README.ja.md`

## ⚙️ Workflow List

| Workflow                      | Trigger                   | Description                          |
|-------------------------------|---------------------------|--------------------------------------|
| `issue-response-codex.yml`    | Issue opened/updated      | Auto-respond to issues               |
| `document-quality-check.yml`  | Markdown files changed    | Documentation quality check          |
| `code-review-codex.yml`       | pull request opened/updated | Code review                        |
| `readme-translation-codex.yml`| `README.md` changed        | Japanese translation                |

## 🔧 Customization

You can customize the Codex prompts in each workflow to suit your project's specific needs.

## 📝 Notes

- Codex minimizes noise with `CODEX_QUIET_MODE=1`
- Enable auto-approval mode with `-a auto-edit`
- All operations are executed with Japanese prompts

## 🤝 Contributing

Feel free to submit issues for improvements or bugs, and pull requests are welcome!

## 📄 License

MIT License