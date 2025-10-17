# 🔁 GitLab Repository Mirroring

## 📄 Introduction
**Repository Mirroring** in GitLab is a feature that allows you to **synchronize code automatically** between different Git repositories.  
You can mirror your repository to or from platforms like **GitHub**, **Bitbucket**, or another **GitLab instance**.  

This is especially useful when:
- You maintain backups of your projects.
- You work across multiple platforms.
- You are migrating repositories.

---

## 🔍 What Is Mirroring?
Mirroring means keeping two repositories **identical** by automatically copying commits, branches, and tags from one to another.  
There are two directions for mirroring:

### 1️⃣ Push Mirroring
- Sends updates **from GitLab → another remote repo**.
- GitLab acts as the **source repository**.
- Every push to GitLab automatically updates the target repo (like GitHub).

### 2️⃣ Pull Mirroring
- Pulls updates **from another repo → GitLab**.
- The external repository acts as the **source**.
- GitLab automatically fetches the latest changes.

---

## ⚙️ How to Set Up Mirroring

### 🔹 For Push Mirroring (GitLab → GitHub)
1. Go to your project in GitLab.  
2. Navigate to **Settings → Repository → Mirroring repositories**.  
3. Under **Mirror a repository**, enter the target repository URL.  
4. Choose **Mirror direction → Push**.  
5. Add your **authentication token or SSH key**.  
6. Click **Mirror repository**.  
7. GitLab will automatically sync your code to GitHub.

### 🔹 For Pull Mirroring (GitHub → GitLab)
1. Go to **Settings → Repository → Mirroring repositories**.  
2. Add the **GitHub repository URL**.  
3. Choose **Mirror direction → Pull**.  
4. Authenticate using a **Personal Access Token (PAT)** from GitHub.  
5. Save changes.  
6. GitLab will pull updates automatically on a schedule.

---

## 🔐 Authentication Methods
You can authenticate mirroring using:
- **SSH Key** – Most secure method.  
- **Personal Access Token (PAT)** – Commonly used for GitHub integration.  
- **Username & Password** – Deprecated method, not recommended.

---

## 🕒 Sync Frequency
- Free Tier: Sync every **hour**.  
- Premium Tier: Sync every **5 minutes**.  
- Manual sync available anytime via the **Mirror now** button.

---

## 🧰 Example Scenario
> You manage your private code in GitLab but want to showcase it publicly on GitHub.

✅ Solution:  
Use **Push Mirroring** from GitLab to GitHub.  
Whenever you push code to GitLab, it’s automatically reflected in GitHub.

---

## 💡 Benefits
- Easy **cross-platform collaboration**
- Automatic **backup and sync**
- Smooth **migration** process
- Saves **manual push effort**

---

## 🧠 Troubleshooting Tips

| Problem | Cause | Solution |
|----------|--------|-----------|
| Authentication failed | Invalid or expired token | Generate a new token with correct scopes |
| Sync not updating | Delay or manual trigger required | Click **Mirror Now** |
| Permission denied | Insufficient repo access | Check access rights or SSH key setup |

---

## 🧾 Example Commands (Manual Way)
```bash
# Clone from GitLab
git clone git@gitlab.com:username/project.git

# Add GitHub remote
git remote add github git@github.com:username/project.git

# Push to GitHub
git push github main
