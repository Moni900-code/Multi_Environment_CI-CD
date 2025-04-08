# Multi-Environment CI/CD Workflow (GitHub Actions)

In modern software development, **safe and structured deployment** is crucial. This CI/CD setup using **GitHub Actions** ensures a smooth and controlled rollout process by separating environments:

- 🚧 **Staging**: Automatically deploys on every push to `main`, ideal for testing and QA.
- 🚀 **Production**: Requires manual approval before deployment, preventing accidental updates and ensuring code is production-ready.

By defining two separate workflows—`staging.yml` and `production.yml`—we maintain reliability and control in our deployment pipeline.

--- 

## Goal:
To deploy the application to two different environments:
- **Staging** (automatic on push)
- **Production** (manual trigger with reviewer approval)

---

## Folder Structure:
```
Canary_Deployment-/
├── .github/
│   └── workflows/
│       ├── staging.yml
│       └── production.yml
├── README.md
```

---

## Step-by-Step Workflow Setup:

### Step 1: Create Workflow Files

Create two workflow files with necessary content:
- `.github/workflows/staging.yml`
- `.github/workflows/production.yml`

> Note: Configure required reviewer for `production` environment in GitHub Settings → Environments.

![Alt Text](reviewers.png)

---

## Step 2: Git Push Commands

After creating the workflows, push them:
```bash
git add .github/workflows/staging.yml .github/workflows/production.yml
git commit -m "Add multi-environment CI/CD workflows"
git push origin main
```

---

## GitHub Result Overview:

### Where to Find the Workflow Results:
1. Go to your GitHub Repository.
2. Click on the **Actions** tab.
3. Two workflows listed: `Deploy to Staging` and `Deploy to Production`.

![Alt Text](stagingS.png)

### Staging Workflow Output:
- Triggered automatically on push to `main`.
- Shows log like:

![Alt Text](staging.png)


### Production Workflow Output:
- Triggered manually via the **Run Workflow** button.
- If reviewer approval is set, it waits for approval.
- Logs will show:

![Alt Text](productionS.png)

## Output:

![Alt Text](production.png)

---
This setup ensures a safe, progressive rollout strategy using GitHub Actions CI/CD.
   
