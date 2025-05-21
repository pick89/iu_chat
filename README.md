# iu_chat 
## Goal
This project in Rust is way to learn to dev using this lamguage.


## 🌿 Branching Strategy: JJ + Git

This document outlines the feature-based development and release strategy using **Jujutsu (jj)** and **GitHub**.

---

### 🔀 Branch Structure

| Branch            | Purpose                              |
|-------------------|--------------------------------------|
| `master`          | Integration branch for validated features |
| `main`            | Production release branch            |
| `feature/*`       | Temporary branches for development   |

---
### 🛠 Development Flow

#### 1. Create feature branch from `master`

```bash
jj checkout master
jj branch create feature/my-feature
jj checkout feature/my-feature
```

Make your changes → commit often:

```bash
jj commit -m "Add feature logic"
```

#### 2. Merge feature 
Once the feature is validated (tested, reviewed):

```bash 
jj checkout master
jj rebase -s feature/my-feature
# Or, if you prefer:
# jj merge feature/my-feature
jj git export
git push origin master
```

Optionally delete the feature branch:
```bash
jj branch forget feature/my-feature
```

#### 3. Push ```master``` to ```main``` for release

Once all features for the release are merged:
```bash
jj checkout main
jj rebase -d master
jj git export
git push origin main