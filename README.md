# DevOps Mirror Repository

This project demonstrates how to mirror a GitLab repository into GitHub — automatically syncing all commits, branches, and merges between the two platforms.

## Project Overview

This repository shows a practical example of GitLab → GitHub repository mirroring.

![](screenshots/overview.png)
Both repositories were created with the same name:

- GitLab Repo: [https://gitlab.com/RajAhire/devops-mirror-repo](https://gitlab.com/RajAhire/devops-mirror-repo)  
- GitHub Repo: [https://github.com/RajAhire-1/devops-mirror-repo](https://github.com/RajAhire-1/devops-mirror-repo)

---

## Setup Steps

### 1. Repository Creation
- Created new repository `devops-mirror-repo` on both GitLab and GitHub.

### 2. GitLab Mirror Configuration
- Go to **Settings → Repository → Mirroring Repositories** in GitLab.
- Click **Add mirror**.
- Enter GitHub repository URL with authentication:
```

[https://RajAhire-1:github_pat_xxxxxxxxxx@github.com/RajAhire-1/devops-mirror-repo.git](https://RajAhire-1:github_pat_xxxxxxxxxx@github.com/RajAhire-1/devops-mirror-repo.git)

````
- Select **Push** direction (GitLab → GitHub).
- Click **Save changes**.

> This ensures every commit or branch update on GitLab automatically pushes to GitHub.

**Screenshot placeholder:**  
![](screenshots/personal_access_token.png)

---

### 3. GitHub Personal Access Token
- Go to **GitHub → Settings → Developer Settings → Personal Access Tokens → Tokens (Classic)**.
- Generate a token with `repo` and `admin:repo_hook` permissions.
- Use this token in the GitLab mirror URL for secure authentication.

---
![](screenshots/personal_token.png)

### 4. Initial Testing
Create `index.html` in GitLab repository:

```html
<h1>Hello, this is my GitLab → GitHub mirror test!</h1>
````

Commit and push:

```bash
git add index.html
git commit -m "Added index.html for mirror test"
git push origin main
```

> File automatically appeared in GitHub repository — mirror verified.

**Screenshot placeholder:**
![](screenshots/sync_repo.png)

---

### 5. Branch & Merge Testing

Create a new branch:

```bash
git checkout -b contact_us
```

Add `contact.html` and push:

```bash
git push origin contact_us
```

* Create a Merge Request on GitLab (`contact_us → main`).
* After merging, GitLab automatically pushes changes to GitHub.

> Merged branch and changes successfully mirrored.
![](screenshots/branch_contact_us.png)
![](screenshots/ready_to__merge.png)

---

## Key Learnings

* GitLab repository mirroring automatically syncs commits, branches, and merges.
* GitHub Personal Access Token ensures secure, continuous synchronization.
* No manual `git push` commands are required after setup.
* Merge requests and branch creations are mirrored automatically.
* Real-time synchronization between GitLab and GitHub.

---

## Mirroring Workflow

```
GitLab (Primary Repository)
        ↓
Push Changes
        ↓
GitLab Mirror Settings
        ↓
GitHub (Mirror)
        ↓
Auto-Sync Complete
```

---

## Technologies Used

* GitLab — source repository
* GitHub — mirror repository
* Git CLI — version control operations
* GitLab Repository Mirroring — core mirroring functionality
* GitHub Personal Access Tokens — secure authentication

---

## Project Structure

```
devops-mirror-repo/
├── index.html          # Test file for mirror verification
├── contact.html        # Branch merge test file
├── README.md           # Project documentation
└── images/             # Screenshots and diagrams
    ├── gitlab-mirror-settings.png
    ├── github-token.png
    ├── successful-sync.png
    └── branch-mirroring.png
```

---

## Quick Start Guide

1. Create repositories on GitLab and GitHub.
2. Generate GitHub Personal Access Token.
3. Configure mirroring in GitLab project settings.
4. Test initial commit and branch creation.
5. Verify automatic synchronization on GitHub.

---

## Author

**Raj Ahire**
📧 [rajahire326@gmail.com](mailto:rajahire326@gmail.com)
🌐 [GitHub](https://github.com/RajAhire-1)
🌐 [GitLab](https://gitlab.com/RajAhire)

