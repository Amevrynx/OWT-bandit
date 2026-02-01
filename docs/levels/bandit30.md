---
layout: default
title: bandit30
---

## bandit30

````markdown
## Access Information

SSH Portal:
ssh bandit30@bandit.labs.overthewire.org -p 2220

Website:
https://overthewire.org/wargames/bandit/

Password for each level is stored inside the current level and used to log into the next.

---

## Level 30 → 31

### Steps to solve
### explanation

After cloning, inspect branches and the commit history to find commits or README versions that reveal the next-level password.

- Clone using the provided SSH URL and port (adjust user/host/path if different):

    - `git clone ssh://bandit30-git@bandit.labs.overthewire.org:2220/home/bandit30-git/repo`

- Inspection workflow:

    - `cd repo`
    - `git branch -a` — list all local and remote branches.
    - `git tag -l` — list tags; tags may point to historical README states.
    - `git show <tag-name>` — show the tag object or the commit it points to.
    - `git show <tag-name>:README` — display the `README` file as it appeared at that tag.
    - `git checkout tags/<tag-name> -b view-tag` — create a branch from the tag to explore the tree safely.
    - `git log --oneline --decorate --graph` — compact view of commit history and branch structure.
    - `git log -p` — show diffs introduced by commits to see when content changed.
    - `git show <commit-id>` — view a specific commit's full diff and metadata.

---
<img src="https://raw.githubusercontent.com/Amevrynx/OWT-bandit/main/bandit30/image.png">

    - `cd repo`
    - `git branch -a` — list all local and remote branches.
    - `git tag -l` — list tags; tags may point to historical README states.
    - `git show <tag-name>` — show the tag object or the commit it points to.
    - `git show <tag-name>:README` — display the `README` file as it appeared at that tag.
    - `git checkout tags/<tag-name> -b view-tag` — create a branch from the tag to explore the tree safely.
    - `git log --oneline --decorate --graph` — compact view of commit history and branch structure.
    - `git log -p` — show diffs introduced by commits to see when content changed.
    - `git show <commit-id>` — view a specific commit's full diff and metadata.

---
````
