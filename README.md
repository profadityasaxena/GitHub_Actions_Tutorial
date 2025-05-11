
# 🚀 GitHub Actions + Vercel Web App Deployment  
## A Tutorial by Aditya Saxena

---

## 🎯 Project Title:
**Auto-Deploy Portfolio Web App with GitHub Actions & Vercel**

---

## 👨‍💻 Author:
**Aditya Saxena**

---

## 🌟 Motivation:
This project demonstrates how to set up a simple HTML/CSS/JavaScript web app and automate its deployment to Vercel using GitHub Actions. The goal is to teach CI/CD basics with GitHub Actions and modern deployment pipelines in a hands-on, developer-friendly manner.

---
## 🧠 Skills Built

| Skill Category          | Description                                                                 |
|------------------------|-----------------------------------------------------------------------------|
| GitHub Actions          | Creating and configuring custom workflows for CI/CD                         |
| CI/CD                   | Automating build and deployment processes using GitHub                      |
| Vercel Deployment       | Integrating GitHub with Vercel for auto-deployment                          |
| Front-End Development   | Building and managing HTML, CSS, JavaScript projects                        |
| Repository Management   | Structuring GitHub repositories for team-ready projects                     |
| GitHub Secrets          | Securing API tokens and environment variables for safe CI/CD operations     |

---

## 🛠️ Step-by-Step Implementation Guide

### ✅ Step 1: Create Project Files
- **Description:** Create an HTML/CSS/JS project folder. Include basic `index.html`, `style.css`, and `script.js` files.
- **Purpose:** This serves as the content of the site being deployed.

---

### ✅ Step 2: Push Project to GitHub
- **Description:** Initialize a Git repo, push code to GitHub under a new public or private repository.
- **Purpose:** Enables GitHub Actions and Vercel to interact with your project.

---

### ✅ Step 3: Link GitHub Repo to Vercel
- **Description:** Log in to [Vercel](https://vercel.com), import the GitHub repo, and choose the project directory.
- **Purpose:** This configures Vercel to listen for pushes to `main`/`master` and deploy automatically.

---

### ✅ Step 4: Create `.github/workflows/deploy.yml`
- **Description:** Add a GitHub Actions workflow YAML file to automate builds, tests, and deployment using GitHub Secrets.
- **Purpose:** Triggers Vercel deployment via GitHub push events, securely using your Vercel token.

```yaml
name: Deploy to Vercel

on:
  push:
    branches:
      - main

jobs:
  deploy:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout code
        uses: actions/checkout@v3

      - name: Deploy to Vercel
        run: |
          curl -X POST https://api.vercel.com/v1/integrations/deploy/prj_XXXXX \
          -H "Authorization: Bearer ${{ secrets.VERCEL_TOKEN }}"
```

> 💡 Make sure to add your `VERCEL_TOKEN` in **GitHub Settings → Secrets and variables → Actions**.

---

### ✅ Step 5: Test the Workflow
- **Description:** Make a change to your code and push it to the `main` branch.
- **Purpose:** GitHub Actions should trigger and the app should deploy automatically via Vercel's API.

---

### ✅ Step 6: Share Your Live Project
- **Description:** Copy the live link from your Vercel dashboard and include it in your project’s `README.md`.
- **Purpose:** Demonstrates end-to-end CI/CD workflow integration with GitHub Actions.

---

## 📦 Final Thoughts:
This tutorial sets the foundation for DevOps integration using GitHub Actions with frontend apps. Once mastered, it can be expanded with custom domains, API integrations, and testing pipelines.

---
# GitHub_Actions_Tutorial

# ✅ 50 GitHub Actions Interview Questions & Answers

---

### 1. What is GitHub Actions?
**Answer:** A CI/CD tool integrated into GitHub for automating workflows such as testing, building, and deploying code.

### 2. What is a workflow?
**Answer:** A YAML-defined automation process triggered by GitHub events like `push`, `pull_request`, etc.

### 3. Where are workflows stored?
**Answer:** Inside the `.github/workflows/` directory of your repository.

### 4. What is a job?
**Answer:** A group of steps that run in the same runner environment.

### 5. What is a runner?
**Answer:** A virtual machine that executes the workflow jobs.

### 6. Can we use custom runners?
**Answer:** Yes, GitHub supports self-hosted runners.

### 7. What triggers a workflow?
**Answer:** Events like `push`, `pull_request`, `schedule`, or manual triggers (`workflow_dispatch`).

### 8. What is `on:` in a workflow?
**Answer:** It defines the event(s) that trigger the workflow.

### 9. What is `workflow_dispatch`?
**Answer:** A manual trigger that allows users to start a workflow via GitHub UI or API.

### 10. How do you restrict workflow to a branch?
**Answer:** Use:
```yaml
on:
  push:
    branches:
      - main
```

### 11. What does `actions/checkout@v3` do?
**Answer:** Checks out your repository code into the runner.

### 12. How do you define environment variables?
**Answer:** Using `env:` at the job or step level.

### 13. What is a step?
**Answer:** A single task within a job (e.g., run a script or action).

### 14. What is a reusable action?
**Answer:** A modular, shareable action defined in its own repo or `.github/actions/`.

### 15. How do you use a reusable action?
**Answer:** With `uses:` syntax, e.g., `uses: actions/setup-node@v3`.

### 16. Can GitHub Actions access secrets?
**Answer:** Yes, via `secrets.NAME` if defined in repo settings.

### 17. How do you pass a secret?
**Answer:** `env: SECRET: ${{ secrets.MY_SECRET }}`

### 18. What is `matrix` in GitHub Actions?
**Answer:** Allows running a job multiple times with different configurations (e.g., Node.js versions).

### 19. How do you cache dependencies?
**Answer:** Using `actions/cache@v3`.

### 20. Can you deploy from GitHub Actions?
**Answer:** Yes, to platforms like Vercel, Heroku, AWS, Azure, etc.

### 21. What is `continue-on-error`?
**Answer:** Allows a step to fail without failing the job.

### 22. How to prevent a workflow from running on forked PRs?
**Answer:** Use `if: github.repository == 'OWNER/REPO'`.

### 23. What does `needs:` do?
**Answer:** Sets job dependencies so that jobs run in sequence.

### 24. Can we set permissions for workflows?
**Answer:** Yes, via `permissions:` block in the workflow file.

### 25. How do you upload artifacts?
**Answer:** Use `actions/upload-artifact@v3`.

### 26. How do you download artifacts?
**Answer:** Use `actions/download-artifact@v3`.

### 27. What is `runs-on:`?
**Answer:** Defines the environment (e.g., `ubuntu-latest`, `windows-latest`).

### 28. What is `default:`?
**Answer:** Sets default shell or working directory for all steps in a job.

### 29. How to debug a workflow?
**Answer:** Use `ACTIONS_STEP_DEBUG=true` secret or add echo/log statements.

### 30. How do you trigger workflows on cron?
**Answer:**
```yaml
on:
  schedule:
    - cron: '0 3 * * *'
```

### 31. What is `concurrency:` used for?
**Answer:** Prevents running multiple workflow instances simultaneously.

### 32. Can workflows trigger other workflows?
**Answer:** Yes, indirectly using repository dispatch or workflow_run events.

### 33. How do you reference an output from another job?
**Answer:** Use `needs.job_id.outputs.output_name`.

### 34. How can you secure secrets?
**Answer:** Use GitHub repository secrets and avoid printing them in logs.

### 35. Can you trigger workflows across repositories?
**Answer:** Yes, using GitHub APIs or `repository_dispatch`.

### 36. What is an action?
**Answer:** A reusable unit of code used in workflows, written in JavaScript or Docker.

### 37. Can GitHub Actions be used in private repos?
**Answer:** Yes, but some features require a paid plan.

### 38. How do you test a workflow locally?
**Answer:** Use tools like [`act`](https://github.com/nektos/act).

### 39. How to cancel a workflow run?
**Answer:** Through the GitHub UI or API.

### 40. What are composite actions?
**Answer:** Actions made from multiple steps defined in `action.yml`.

### 41. How do you define outputs in steps?
**Answer:**
```yaml
id: my_step
run: echo "::set-output name=msg::hello"
```

### 42. What are GitHub-hosted runners?
**Answer:** VMs provided by GitHub that run your workflows in a clean environment.

### 43. Can you reuse workflows?
**Answer:** Yes, using `workflow_call`.

### 44. What is a badge in GitHub Actions?
**Answer:** A status image showing the current build state.

### 45. How do you add a badge?
**Answer:** Use the markdown link from the Actions tab.

### 46. What is `strategy.fail-fast`?
**Answer:** Stops all matrix jobs when one fails.

### 47. What is a `deployment` environment?
**Answer:** Named environments like `staging`, `production` with optional approval rules.

### 48. Can GitHub Actions use Docker?
**Answer:** Yes, via `container:` or Docker actions.

### 49. How do you set default shell?
**Answer:** Use `shell: bash` or `shell: pwsh` in steps.

### 50. What is the first step to use GitHub Actions?
**Answer:** Create a `.github/workflows/main.yml` file in your repository.
