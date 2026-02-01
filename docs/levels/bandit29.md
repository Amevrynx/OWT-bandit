---
layout: default
title: bandit29
---

## bandit29

````markdown
## Access Information

SSH Portal:
ssh bandit29@bandit.labs.overthewire.org -p 2220

Website:
https://overthewire.org/wargames/bandit/

Password for each level is stored inside the current level and used to log into the next.

---

## Level 29 → 30

### Steps to solve
```bash
clone the repo using the given link but add the port after the domain address

git clone ssh://bandit29-git@bandit.labs.overthewire.org:2220/home/bandit29-git/repo
cd repo
cat README
git branch -a 

git checkout dev     

git show <commit-id> 

then inspect the changes
```

### explanation

After cloning, inspect branches and the commit history to find commits or README versions that reveal the next-level password.

- Clone using the provided SSH URL and port (adjust user/host/path if different):

    - `git clone ssh://bandit29-git@bandit.labs.overthewire.org:2220/home/bandit29-git/repo`

- Recommended inspection workflow:

    - `cd repo`
    - `git branch -a` — list all local and remote branches; look for `dev` or similarly named branches.
    - `git checkout dev` — switch to the `dev` branch if it exists (`git checkout -b dev origin/dev` if needed).
    - `git log --oneline --decorate --graph` — compact view of commit history and branch structure.
    - `git log -p` — show diffs introduced by commits to see when content changed.
    - `git show <commit-id>` — view a specific commit's full diff and metadata.
    - `git show <commit-id>:README` — display the `README` file as it appeared in that commit.

---
<img src="https://raw.githubusercontent.com/Amevrynx/OWT-bandit/main/bandit29/image.png">
````
