
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
- **Purpose:** This configures Vercel to listen for pushes to main/master and deploy automatically.

---

### ✅ Step 4: Create `.github/workflows/deploy.yml`
- **Description:** Add a GitHub Actions workflow YAML file to automate builds or tests.
- **Purpose:** Triggers Vercel deployment via GitHub push events. You can also run lint/test steps here.

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
      - uses: actions/checkout@v3

      - name: Trigger Vercel Deployment
        run: echo "Deployment triggered by GitHub Actions"
```

---

### ✅ Step 5: Test the Workflow
- **Description:** Make a change to your code and push it to the `main` branch.
- **Purpose:** GitHub Actions should trigger and the app should deploy on Vercel.

---

### ✅ Step 6: Share Your Live Project
- **Description:** Copy the live link from Vercel and add it to your GitHub README.
- **Purpose:** Demonstrates end-to-end automation and deployment.

---

## 📦 Final Thoughts:
This tutorial sets the foundation for DevOps integration using GitHub Actions with frontend apps. Once mastered, it can be expanded with custom domains, API integrations, and testing pipelines.

---
# GitHub_Actions_Tutorial
