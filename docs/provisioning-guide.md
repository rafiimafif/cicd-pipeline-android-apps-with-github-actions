# 🆓 Zero-Cost Provisioning Guide

Follow these steps to set up the full pipeline at **no cost**.

## 1. SonarCloud (Code Quality)
1. Log in to [sonarcloud.io](https://sonarcloud.io) via GitHub.
2. Create a project and name it.
3. Go to **Security > Generate Token** and copy it.

## 2. Firebase (App Distribution)
1. Create a project on [firebase.google.com](https://firebase.google.com).
2. Register your Android app.
3. Enable **App Distribution**.
4. Go to **Project Settings > Service Accounts** and generate a new JSON key.

## 3. GitHub Secrets
Add these to your repo settings:
- `SONAR_TOKEN`: From SonarCloud.
- `FIREBASE_APP_ID`: From Firebase settings.
- `CREDENTIAL_FILE_CONTENT`: The full JSON text from the Firebase key.
- `SONAR_ORGANIZATION`: `rafiimafif`
- `SONAR_PROJECT_KEY`: `rafiimafif_cicd-pipeline-android-apps-with-github-actions-`
