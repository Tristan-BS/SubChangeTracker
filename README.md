<div align="center">
  <img src="Images/Logo-Transparent.png" alt="Logo">
  <h4>Automatically get submodule Changes</h4>
</div>

<div align="center">
  <a href="https://github.com/Tristan-BS/SubChangeTracker/actions/workflows/SubChangeTracker.yml" style="display: inline-block;">
    <img src="https://github.com/Tristan-BS/SubChangeTracker/actions/workflows/SubChangeTracker.yml/badge.svg" alt="Check Submodules for Updates">
  </a>
  <a href="https://opensource.org/licenses/MIT" style="display: inline-block; margin-left: 10px;">
    <img src="https://img.shields.io/badge/license-MIT-red.svg" alt="License">
  </a>
  <a href="https://github.com/Tristan-BS/SubChangeTracker" style="display: inline-block; margin-left: 10px;">
    <img src="https://img.shields.io/badge/Open%20Contributor-Welcome-brightgreen.svg" alt="Open Contributor: Welcome">
  </a>
  <a href="https://github.com/Tristan-BS/SubChangeTracker" style="display: inline-block; margin-left: 10px;">
    <img src="https://img.shields.io/badge/Open%20Current-Version-blue.svg" alt="V1.5.3: Welcome">
  </a>
</div>

# SubChangeTracker
This workflow checks for updates to submodules, performs the updates, creates or updates a branch, and pushes the changes back to the created branch, running three times a day at 00:00, 06:00, 12:00, and 18:00 UTC.


# How to deploy a submodule:
go to your local repository and type:
```
git submodule add https://github.com/Tristan-BS/SCT-TestRepo.git
```
or 
```
git submodule add https://github.com/Tristan-BS/SCT-TestRepo.git submodules
```
Now you can finally commit and push your changes.


# Deploy this Workflow into YOUR Repository

## 1. Generate a Personal Token
- Click on your Profile Picture
- Go to Settings
- On the left side click on <> Developer Settings
- Open Dropdown Personal access tokens
- Click on Fine-grained tokens
- Click on Generate new token
- Name it as you like or name it `SubChangeTrackerToken`
- Add an Expiration date as you like
- Add a Description if you like to
- Set the Repository access to `All Repositories`
- Set following Repository Read and write Permissions
1. Actions
2. Commit statuses
3. Contents
4. Deployments
5. Workflows
- Generate Token
- Copy your Token

### 2. Add a Repository Secret
- Now go to your Repository and click on Settings
- Open Dropdown Secrets and variables
- Click on Actions
- Click on New Repository secret
- Choose a name as you like or name it `SubChangeTrackerToken`
- Press on Add secret
> [!CAUTION]
> If you want another name for your Repository secret, you have to change your `SubChangeTracker.yml` file!

### 3. Create and execute Workflow
- Press on Actions
- New Workflow
- set up a workflow yourself
- Copy paste my workflow into it and name it SubChangeTracker
- Commit Changes
- To test it just go into your workflow into the file and press on `View Runs`
- Press `Run workflow` -> make sure `main` branch is selected
- Refresh your page and the workflow is running
- And now you will see a Repository appeared and you can `Compare & pull Request` if you like to

# Changelog
- V1.5.3
    - Added 06:00 UTC
