# 🆓 Zero-Cost Provisioning Guide

Follow these steps to set up the full pipeline at **no cost**.

## 1. SonarCloud (Code Quality)
1. Log in to [sonarcloud.io](https://sonarcloud.io) via GitHub.
2. Create a project and name it.
3. Go to **Security > Generate Token** and copy it.

## 2. Firebase (App Distribution)
1. Create a project on [firebase.google.com](https://firebase.google.com).
2. Register your Android app. **Important:** The package name MUST exactly match your `applicationId` in `app/build.gradle`.
3. Enable **App Distribution**.
4. Go to **Testers & Groups** and create a group named exactly `internal-testers`.
5. Go to **Project Settings > Service Accounts** and generate a new JSON key.
6. Open [Google Cloud IAM](https://console.cloud.google.com/iam-admin/iam) and grant your new service account the **Firebase App Distribution Admin** role.

## 3. GitHub Secrets
Add these to your repo settings (**Settings > Secrets and variables > Actions**):
- `SONAR_TOKEN`: From SonarCloud.
- `SONAR_ORGANIZATION`: Your SonarCloud Org ID (e.g., `rafiimafif`).
- `SONAR_PROJECT_KEY`: Your project key (e.g., `rafiimafif_cicd-pipeline...`).
- `SONAR_HOST_URL`: `https://sonarcloud.io`
- `FIREBASE_APP_ID`: From Firebase settings. Must be format `1:NUMBER:android:HEX`.
- `CREDENTIAL_FILE_CONTENT`: The full JSON text from the Firebase key.
