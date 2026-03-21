# 🚀 Android CI/CD Pipeline: Zero-Cost Automation

![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=for-the-badge&logo=github-actions&logoColor=white)
![SonarCloud](https://img.shields.io/badge/SonarCloud-F3702A?style=for-the-badge&logo=sonarcloud&logoColor=white)
![Firebase](https://img.shields.io/badge/Firebase-FFCA28?style=for-the-badge&logo=firebase&logoColor=black)

## 📌 Overview

This repository showcases a professional, **100% free** CI/CD pipeline for Android applications. It transforms a legacy project into a modern powerhouse that automatically scans, builds, stores, and delivers APKs.

### ✅ Key Features

- **Automated Builds** – Compiles Android apps with Gradle (JDK 11).
- **Code Quality Monitoring** – Automated analysis with **SonarCloud** (JDK 17).
- **Zero-Cost Storage** – Permanent APK hosting via **GitHub Releases**.
- **Resilient Distribution** – Direct delivery to testers via **Firebase CLI**.
- **Multi-branch Strategy** – CI on all branches, CD only on `qa` and `main`.

---

## 🏗️ Architecture

```mermaid
graph TD
    A[📦 Developer Push] --> B{Branch Check}
    B -->|Develop| C[🛠️ Build & Sonar Scan]
    B -->|QA / Main| D[🛠️ Build & Sonar Scan]
    D --> E[🎁 Create GitHub Release]
    E --> F[📲 Push to Firebase Distro]
    F --> G[📧 Internal Testers]
```

---

## 🛠️ Tech Stack

| Category | Technology |
|---|---|
| **CI/CD** | GitHub Actions |
| **Code Quality** | SonarCloud |
| **Artifact Storage** | GitHub Releases |
| **Distribution** | Firebase App Distribution (CLI) |
| **Build Tool** | Gradle |
| **Language** | Kotlin + Java |

---

## 📖 Success Guides

The entire journey and setup instructions are documented in these detailed guides:

1.  **[🚀 DevOps Journey](docs/devops-journey.md)** — How this project was transformed from legacy to modern.
2.  **[📱 Beginner's Handbook](docs/beginner-handbook.md)** — The "App Factory" explained for a non-technical audience.
3.  **[🆓 Provisioning Guide](docs/provisioning-guide.md)** — Step-by-step setup for a zero-cost pipeline.

---

## 🔐 Required Secrets

To replicate this setup, add these secrets to your GitHub repository:

| Secret | Description |
|---|---|
| `SONAR_TOKEN` | Auth token from SonarCloud |
| `FIREBASE_APP_ID` | App ID from Firebase Project |
| `CREDENTIAL_FILE_CONTENT` | Firebase Service Account JSON text |
| `SONAR_ORGANIZATION` | Your SonarCloud Org ID |
| `SONAR_PROJECT_KEY` | Your SonarCloud Project Key |

---

## 🛠️ Author

**Rafii Mafif** — DevOps Engineer
- 🐙 **GitHub**: [@rafiimafif](https://github.com/rafiimafif)

---

> ⭐ If you found this helpful, consider starring the repo!
