<div align="center">

![Image](https://github.com/user-attachments/assets/04c68e93-e88b-45d2-bfab-8060c906dd7c)

# [Codex-Workspace](https://github.com/Sunwood-ai-labs/Codex-Workspace)

<p align="center">
  <img src="https://img.shields.io/badge/OpenAI_Codex-412991?style=for-the-badge&logo=openai&logoColor=white" alt="OpenAI Codex">
  <img src="https://img.shields.io/badge/GitHub_Actions-2088FF?style=for-the-badge&logo=github-actions&logoColor=white" alt="GitHub Actions">
  <img src="https://img.shields.io/badge/Automation-000000?style=for-the-badge&logo=robot&logoColor=white" alt="Automation">
</p>

<p align="center">
  A simple and efficient collection of GitHub Actions workflows utilizing OpenAI Codex
</p>

</div>

## 🚀 Overview

This repository is a lightweight collection of workflows that leverage the powerful capabilities of OpenAI Codex within GitHub Actions to automate your repository. By avoiding heavy processing and focusing on the essential features, it achieves both simplicity and efficiency.

## ✨ Features

- 💬 **Issue Auto-Response**: Codex analyzes new or updated issues and provides appropriate replies or fixes
- 📝 **Document Quality Check**: Automatically reviews the quality of README and other documentation, and suggests improvements via PRs
- 🔍 **Code Review**: Automatically reviews code in PRs and suggests improvements
- 🌐 **README Translation**: Automatically translates README.md into Japanese and creates a PR

## 📦 Setup

Follow the steps below to initialize the repository and configure the required environment variables and secrets.

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

* `OPENAI_API_KEY`: OpenAI API key  
* `GITHUB_TOKEN`: GitHub API token (optional; automatically provided in GitHub Actions)  
* `CODEX_QUIET_MODE`: Codex quiet mode (e.g., `1`)  

### 3. Set up Secrets (for GitHub Actions)

In your GitHub repository settings > Secrets, add the following:

* `OPENAI_API_KEY`: OpenAI API key  

### 4. Enable the workflows

The workflow files in `.github/workflows/` will be automatically enabled.

## 🛠️ Usage

### Issue Auto-Response

1. Create or update an issue
2. Codex analyzes the content and posts an appropriate response
3. If code fixes are needed, it automatically creates a PR

### Document Quality Check

1. Push a Markdown file or create a PR
2. Codex checks the quality and automatically applies improvements
3. Proposes the changes as a PR

### Code Review

1. Create a new PR
2. Codex reviews the changes
3. Posts improvement suggestions as comments

### README Translation

1. Update README.md
2. Automatically generates a Japanese version
3. Creates a PR as README.ja.md

## ⚙️ Workflow List

| Workflow                            | Trigger                         | Description                                  |
|-------------------------------------|---------------------------------|----------------------------------------------|
| `auto-release-notes.yml`            | push (tag `v*`)                 | Automatic release notes generation           |
| `issue-response-codex.yml`          | Issue creation/edit, comment posting | Auto-response to issues                 |
| `beta-code-review-codex.yml`        | PR creation/update              | Code review (beta)                           |
| `beta-document-quality-check.yml`   | Markdown file changes           | Document quality check (beta)                |
| `beta-readme-translation-codex.yml` | README.md changes               | README translation (beta)                    |

※ The `beta-*.yml` files are in beta. They are experimental features, so use with caution.

## 🔧 Customization

You can customize the Codex prompts for each workflow to adjust their behavior to your project's needs.

## 📝 Notes

- Codex minimizes noise with `CODEX_QUIET_MODE=1`
- Use the `-a auto-edit` option to enable auto-approve mode
- All processes are executed with Japanese prompts

## 🤝 Contributions

Feel free to submit improvement suggestions or bug reports via Issues. PRs are also welcome!

## 📄 License

MIT License