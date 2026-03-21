# 🚀 End-to-End CI/CD Pipeline for Android Apps with GitHub Actions

![GitHub Actions](https://imgur.com/XNUS0pA.png)

## 📌 Overview

This repository demonstrates how to build a fully automated **CI/CD pipeline** for Android applications using **GitHub Actions**. The pipeline ensures seamless **building, testing, and deployment**, allowing developers to focus on writing code while automation handles the rest.

### ✅ Key Features

- **Automated Builds** – Compile Android projects with Gradle
- **Continuous Integration** – Run unit and instrumentation tests with JaCoCo coverage
- **Code Quality Checks** – Static analysis with Android Lint & SonarQube
- **Artifact Management** – Store timestamped APK/AAB files securely on JFrog Artifactory (AWS EC2)
- **Secure Deployments** – Dynamic AWS Security Group IP whitelisting for runner access
- **Team Notifications** – Real-time pipeline status via Microsoft Teams Webhook
- **Multi-branch Strategy** – CI on all branches, CD only on `qa` and `main`

---

## 🏗️ Architecture

```
Developer Push / PR
        │
        ▼
 ┌──────────────────────────────────────┐
 │        CI Build Job (all branches)   │
 │  Checkout → JDK 11 → Lint → Build   │
 │  → JaCoCo → SonarQube → Upload APK  │
 │  → MS Teams Notification             │
 └──────────────┬───────────────────────┘
                │ (qa / main only)
                ▼
 ┌──────────────────────────────────────┐
 │        CD Deploy Job                 │
 │  Download APK → Whitelist IP (AWS)   │
 │  → Upload to JFrog Artifactory       │
 │  → Remove IP → MS Teams Notification │
 └──────────────────────────────────────┘
```

---

## 🛠️ Tech Stack

| Category | Technology |
|---|---|
| CI/CD | GitHub Actions |
| Build | Gradle 7 |
| Language | Kotlin + Java 8 |
| Code Quality | SonarQube + Android Lint |
| Code Coverage | JaCoCo |
| Artifact Repo | JFrog Artifactory (AWS EC2) |
| Cloud | AWS EC2 + Security Groups |
| Notifications | Microsoft Teams |

---

## 📖 Workflows

| Workflow | File | Trigger |
|---|---|---|
| Android CI and CD | `android.yml` | Push/PR to main, qa, develop |
| Clear Cache | `clear-caches.yml` | After CI/CD completes |
| Delete Artifacts | `delete-artifacts.yml` | Scheduled / Manual |

---

## 🔐 Required GitHub Secrets

```
SONAR_TOKEN           - SonarQube auth token
SONAR_HOST_URL        - SonarQube server URL
CI_GITHUB_TOKEN       - GitHub Personal Access Token
MS_TEAMS_WEBHOOK_URI  - MS Teams Incoming Webhook
AWS_ACCESS_KEY_ID     - AWS IAM key
AWS_SECRET_ACCESS_KEY - AWS IAM secret
JFROG_SG_ID           - AWS Security Group ID
JF_URL                - JFrog Artifactory URL
JF_ACCESS_TOKEN       - JFrog access token
JF_USER               - JFrog username
JF_PASSWORD           - JFrog password
```

---

## 📖 Step-by-Step Guide

Check out the complete **blog tutorial with screenshots** here:
📌 **[End-to-End CI/CD Pipeline Using GitHub Actions](https://blog.prodevopsguytech.com/end-to-end-cicd-pipeline-using-github-actions-for-android-application)**

---

## 🛠️ Author

**Rafii Mafif** — DevOps Engineer

- 🐙 **GitHub**: [@rafiimafif](https://github.com/rafiimafif)

---

> ⭐ If you found this helpful, consider starring the repo and sharing it with your network!
