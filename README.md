# 🚀 Automated Static Website Deployment Pipeline

A lightweight DevOps project that automates the deployment of a static HTML website to Amazon Web Services (AWS) S3 using **GitHub Actions**.

Whenever a change is pushed to the `main` branch, the pipeline triggers, authenticates with AWS, and synchronizes the frontend files immediately.
############## Folder and file layout
devops-simple-s3-pipeline/
├── .github/
│   └── workflows/
│       └── deploy.yml       # GitHub Actions workflow file
├── src/
│   ├── error.html           # Page shown for 404 errors
│   └── index.html           # Your main live website homepage
├── .gitignore               # Files git should ignore
└── README.md                # Project documentation


## 🏗️ Architecture Design
`Local Git Push` ➔ `GitHub Actions Pipeline` ➔ `AWS S3 Bucket (Static Web Hosting)` ➔ `Live Web URL`

## 🛠️ Tech Stack
* **CI/CD Automation:** GitHub Actions
* **Cloud Hosting Platform:** AWS S3
* **Frontend Basics:** HTML5 / CSS3

## 📋 AWS Setup Prerequisites
1. Create a Public S3 bucket on AWS named after your project (e.g., `my-unique-devops-bucket-2026`).
2. Turn on **Static Website Hosting** in your S3 Bucket properties dashboard.
3. Attach a bucket policy to allow public reads (`s3:GetObject`).

## 🔒 GitHub Repository Secrets Configured
To enable the pipeline to work, configure these variables under your GitHub repo's **Settings > Secrets and variables > Actions**:
* `AWS_ACCESS_KEY_ID` - Your AWS security credential key ID.
* `AWS_SECRET_ACCESS_KEY` - Your AWS secret access key.
* `AWS_S3_BUCKET_NAME` - The exact name of your AWS S3 bucket.

## 💻 Local Setup Commands
```bash
git init
git add .
git commit -m "feat: initial commit of automated simple s3 pipeline website"
git branch -M main
git remote add origin https://github.com
git push -u origin main
```
