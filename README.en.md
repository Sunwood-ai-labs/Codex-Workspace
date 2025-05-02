 <div align="center">

 ![Image](https://github.com/user-attachments/assets/04c68e93-e88b-45d2-bfab-8060c906dd7c)

 # [Codex-Workspace](https://github.com/Sunwood-ai-labs/Codex-Workspace)

 <p align="center">
   <img src="https://img.shields.io/badge/OpenAI_Codex-412991?style=for-the-badge&logo=openai&logoColor=white" alt="OpenAI Codex">
   <img src="https://img.shields.io/badge/GitHub_Actions-2088FF?style=for-the-badge&logo=github-actions&logoColor=white" alt="GitHub Actions">
   <img src="https://img.shields.io/badge/Automation-000000?style=for-the-badge&logo=robot&logoColor=white" alt="Automation">
 </p>

 <p align="center">
   A simple and efficient set of GitHub Actions workflows leveraging OpenAI Codex
 </p>

 </div>

 ## 🚀 Overview

 This repository is a lightweight collection of workflows that leverage the powerful capabilities of OpenAI Codex within GitHub Actions to automate your repository. By avoiding heavy processing and focusing on minimal necessary functionality, it achieves both simplicity and efficiency.

 ## ✨ Features

 - 💬 **Automatic Issue Responses**: Codex analyzes new or updated issues and provides appropriate replies or fixes
 - 📝 **Documentation Quality Check**: Automatically reviews the quality of READMEs and documentation, proposing improvements via pull requests
 - 🔍 **Code Review**: Automatically reviews pull request code and suggests improvements
 - 🌐 **README Translation**: Automatically translates README.md into Japanese and creates a pull request
 - 📜 **Automatic Release Notes Generation**: Generates release notes with Codex upon tag push and creates a GitHub Release

 ## 📦 Setup

 Follow the steps below to initialize the repository and set up required environment variables and secrets.

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

 In the repository's Settings > Secrets, add the following:

 * `OPENAI_API_KEY` : OpenAI API key

 ### 4. Enable Workflows

 The workflow files in `.github/workflows/` will be automatically enabled.

 ## 🛠️ Usage

 ### Automatic Issue Responses

 1. Create or update an issue
 2. Codex analyzes the content and posts an appropriate response
 3. If code fixes are needed, a pull request is automatically created

 ### Documentation Quality Check

 1. Push Markdown files or open a pull request
 2. Codex checks quality and automatically applies improvements
 3. Suggested changes are proposed via a pull request

 ### Code Review

 1. Create a new pull request
 2. Codex reviews the changes
 3. Improvement suggestions are posted as comments

 ### README Translation

 1. Update README.md
 2. An automatic Japanese version is created
 3. A pull request is created with README.ja.md

 ### Automatic Release Notes Generation

 1. Push a tag in the `v*` format
 2. The `auto-release-notes` workflow runs, analyzes changes, and generates `release_notes.md`
 3. A GitHub Release is created based on `release_notes.md`

 ## ⚙️ Workflow List

 | Workflow | Trigger | Description |
 |----------|-----------------------|----------------------------|
 | `auto-release-notes.yml` | push (tag `v*`) | Automatic release notes generation |
 | `issue-response-codex.yml` | Issue creation/edit, comment posting | Automatic issue responses |
 | `beta-code-review-codex.yml` | PR creation/update | Code review (beta) |
 | `beta-document-quality-check.yml` | Markdown file changes | Documentation quality check (beta) |
 | `beta-readme-translation-codex.yml` | README.md changes | README translation (beta) |

 Note: `beta-*.yml` workflows are in beta. Use with caution as they are experimental.

 ## 🔧 Customization

 You can customize the Codex prompts in each workflow to tailor behavior to your project's needs.

 ## 📝 Notes

 - By setting `CODEX_QUIET_MODE=1`, Codex minimizes noise
 - Use the `-a auto-edit` option to enable automatic approval mode
 - All operations are performed with Japanese prompts

 ## 🤝 Contribution

 Please report improvements or bugs via an issue. Pull requests are also welcome!

 ## 📄 License

 MIT License