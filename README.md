# DevOps Task Demo

This repository demonstrates three DevOps tasks:

## Task 1: GitHub Actions Artifact Upload
- **Files:** `sample.txt`, `sample.json`, `sample.csv`
- **Workflow:** `.github/workflows/artifact-upload.yml`
- **Trigger:** Push to main or manual dispatch (`workflow_dispatch`)
- **Artifact Name:** `sample-files`
- **Retention:** 7 days

### How to run:
1. Push changes to main branch, or
2. Go to GitHub Actions UI → Run `Upload Artifact` workflow manually

The artifact will be available in the workflow run summary for download.

---

## Task 2: Build Docker Image
- **Base Image:** `ubuntu:latest`
- **Tools Installed:**
  - Python 3
  - PowerShell
  - .NET CLI
- **Build Output:** Image saved as tar file

### Build locally:
```bash
docker build -t ubuntu-tools:latest -f Dockerfile .
docker save ubuntu-tools:latest -o ubuntu-tools.tar
```

---

## Task 3: Verify Container Tools
- **Workflow:** `.github/workflows/verify-container.yml` (to be created)
- **Verification:** Run container and print tool versions
  - `python --version`
  - `pwsh --version`
  - `dotnet --version`

---

## Repository Structure
```
DevOps-Task-Demo/
├── README.md
├── Dockerfile (Task 2)
├── sample.txt (Task 1)
├── sample.json (Task 1)
├── sample.csv (Task 1)
└── .github/
    └── workflows/
        ├── artifact-upload.yml (Task 1)
        └── verify-container.yml (Task 3 - to be created)
```

---

## Setup Instructions

1. Create a new repository on GitHub (https://github.com/new)
2. Clone this repository locally or add it as a remote
3. Push to GitHub:
   ```bash
   git remote add origin https://github.com/YOUR_USERNAME/DevOps-Task-Demo.git
   git branch -M main
   git push -u origin main
   ```
4. GitHub Actions workflows will trigger automatically on push
5. View results in GitHub Actions tab
