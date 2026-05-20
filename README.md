<div align="center">
  <img src="Images/Logo-Transparent.png" alt="Logo">
  <h4>Automatically get submodule Changes</h4>
</div>

<div align="center">
  <a href="https://github.com/Tristan-BS/SubChangeTracker/actions/workflows/SubChangeTracker.yml" style="display: inline-block;">
    <img src="https://github.com/Tristan-BS/SubChangeTracker/actions/workflows/SubChangeTracker.yml/badge.svg" alt="Check Submodules for Updates">
  </a>
  <a href="https://github.com/Tristan-BS/SubChangeTracker" style="display: inline-block; margin-left: 10px;">
    <img src="https://img.shields.io/badge/Open%20Contributor-Welcome-brightgreen.svg" alt="Open Contributor: Welcome">
  </a>
  </br>
  <a href="https://opensource.org/licenses/MIT" style="display: inline-block; margin-left: 10px;">
    <img src="https://img.shields.io/badge/license-MIT-red.svg" alt="License">
  </a>
  <a href="https://github.com/Tristan-BS/SubChangeTracker/releases/tag/v1.5.3" style="display: inline-block; margin-left: 10px;">
    <img src="https://img.shields.io/badge/Current%20Version-V1.5.3-blue.svg" alt="Current Version: V1.5.3">
  </a>
</div>

# SubChangeTracker
This workflow checks for updates to submodules, performs the updates, creates or updates a branch, and pushes the changes back to the created branch.

> [!IMPORTANT]
> Before using this workflow in your own repository, you should edit the workflow file first.
> It is recommended to disable the automatic `schedule` triggers at the beginning and only use `workflow_dispatch` for manual testing.
> After everything works correctly in your repository, you can re-enable the scheduled runs.

## Recommended first step: edit the workflow
Before running the workflow, open the `SubChangeTracker.yml` file and adjust the trigger section.

Example:

```yaml
on:
  workflow_dispatch:
  # Re-enable automatic runs by uncommenting the lines below.
    schedule:
      - cron: '0 0 * * *'
      - cron: '0 6 * * *'
      - cron: '0 12 * * *'
      - cron: '0 18 * * *'
```

This means:
- the workflow is **manual only** at first
- it will **not run automatically**
- you can safely test it before enabling scheduled execution

# How to deploy a submodule:
Go to your local repository and type:

```bash
git submodule add https://github.com/Tristan-BS/SCT-TestRepo.git
```

or

```bash
git submodule add https://github.com/Tristan-BS/SCT-TestRepo.git submodules
```

Now you can finally commit and push your changes.

# Deploy this Workflow into YOUR Repository

## 1. Generate a Personal Token
- Click on your profile picture
- Go to **Settings**
- On the left side click on **Developer settings**
- Open the **Personal access tokens** dropdown
- Click on **Fine-grained tokens**
- Click on **Generate new token**
- Name it as you like or name it `SubChangeTrackerToken`
- Add an expiration date as you like
- Add a description if you want to
- Set the repository access to `All repositories`
- Set the following repository read and write permissions:
  1. Actions
  2. Commit statuses
  3. Contents
  4. Deployments
  5. Workflows
- Generate token
- Copy your token

## 2. Add a Repository Secret
- Go to your repository and click on **Settings**
- Open **Secrets and variables**
- Click on **Actions**
- Click on **New repository secret**
- Choose a name as you like or name it `SubChangeTrackerToken`
- Press **Add secret**

> [!CAUTION]
> If you want another name for your repository secret, you have to change your `SubChangeTracker.yml` file.

## 3. Create the Workflow
- Press on **Actions**
- Click **New workflow**
- Click **set up a workflow yourself**
- Copy and paste the workflow into the file
- Name it `SubChangeTracker.yml`
- **Before running it, edit the workflow file and keep only `workflow_dispatch` enabled**
- Commit changes

## 4. Test the Workflow manually
- Open your workflow
- Press on **Run workflow**
- Make sure the `main` branch is selected
- Refresh the page and the workflow should start running
- After that, you should see the created update branch and can open a **Compare & pull request** if you want to

# Changelog
- V1.5.3
  - Added 06:00 UTC
