---
layout: default
title: bandit28
---

## bandit28

````markdown
## Access Information

SSH Portal:
ssh bandit28@bandit.labs.overthewire.org -p 2220

Website:
https://overthewire.org/wargames/bandit/

Password for each level is stored inside the current level and used to log into the next.

---

## Level 28 → 29

### Steps to solve
```bash
clone the repo using the given link but add the port after the domain address

git clone ssh://bandit28-git@bandit.labs.overthewire.org:2220/home/bandit27-git/repo
cd repo
cat README
git log
git show <commit-id>

then check the related changes
```

<img src="https://raw.githubusercontent.com/Amevrynx/OWT-bandit/main/bandit28/image.png">

### explanation

After cloning the repository you should inspect the commit history to find changes that reveal the next-level password.

- Clone with the explicit SSH URL and port (adjust user/host/path as provided):

    - `git clone ssh://bandit28-git@bandit.labs.overthewire.org:2220/home/bandit28-git/repo`

    The `ssh://user@host:port/path` form tells Git to use the specified SSH port.

- common inspection workflow:

    - `cd repo`
    - `git log --oneline --decorate --graph` — get a compact view of commits and branches; copy any commit IDs of interest.
    - `git log -p` — show diffs introduced by each commit (useful to see when secrets were added/removed).
    - `git show <commit-id>` — show the full patch and metadata for a single commit; `git show <commit-id>:README` prints the `README` file as it appeared in that commit.
    - `git show <commit-id> --name-only` — list files changed in that commit.
---
````
