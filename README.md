# 🔐 GitHub Repository Access Checker

This Bash script helps you **list all users who have *read access* (pull permissions)** to a specific repository in a GitHub organization (or personal repo).
It uses the **GitHub REST API v3** and requires a **personal access token (PAT)** with the right permissions. 🚀

---

## 🌟 My Journey

This is **my first DevOps project** 🎉 and I’m super **enthusiastic 💪** to build and share it!
Starting small but learning big — this script is my step into the **DevOps world** 🛠️🚀

---

## 📋 Features

* ✅ Fetch collaborators from any GitHub repo
* ✅ Filter only those with **read access** (pull permission)
* ✅ Works for both **personal repos** and **organization repos**
* ✅ Simple & lightweight using `curl` + `jq`

---

## ⚙️ Requirements

Before running the script, make sure you have:

* 🐧 **Bash** (Linux/macOS) or WSL on Windows
* 📡 `curl` installed
* 🛠️ `jq` installed (for parsing JSON responses)
* 🔑 A **GitHub Personal Access Token** (classic or fine-grained with `repo` scope)

---

## 🚀 Usage

### 1️⃣ Save the script

Save the script as `list_read_access.sh`

```bash
chmod +x list_read_access.sh
```

### 2️⃣ Set your credentials

Export your GitHub username and token in your terminal:

```bash
export username="your_github_username"
export token="your_personal_access_token"
```

### 3️⃣ Run the script

Pass the **repo owner** and **repo name** as arguments:

```bash
./list_read_access.sh ORG_NAME REPO_NAME
```

👉 Example:

```bash
./list_read_access.sh octocat hello-world
```

---

## 📊 Example Output

```
Listing users with read access to octocat/hello-world...
Users with read access to octocat/hello-world:
alice
bob
charlie
```

If no users are found:

```
No users with read access found for octocat/hello-world.
```

---

## 📝 Notes

* 🔒 Your **token must have `repo` access** (or org-level permissions if you’re checking private org repos).
* 🏢 Works across **GitHub organizations** — just provide the org name as the repo owner.
* 🧹 Keep your token safe! Don’t commit it in code. Use `export` or a `.env` file.

---

## 🎯 Why use this?

* ✅ Audit repository access in organizations
* ✅ Quickly see who has pull rights
* ✅ Useful for **security reviews & compliance**

---

💡 Pro Tip: You can modify the script to check for **write** (`push`) or **admin** access by adjusting the filter in the `jq` command. 😉
