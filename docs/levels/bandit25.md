<img src="https://raw.githubusercontent.com/Amevrynx/OWT-bandit/main/bandit25/image.png">

### explanation

## bandit25

````markdown
## Access Information

SSH Portal:
ssh bandit25@bandit.labs.overthewire.org -p 2220

Website:
https://overthewire.org/wargames/bandit/

Password for each level is stored inside the current level and used to log into the next.

---

## Level 25 → 26

### Steps to solve
```bash
use the sshkey provided

ssh -i bandit26.sshkey bandit26@bandit.labs.overthewire.org -p 2220
```
---
<img src="image.png">

### explanation

This level uses the provided SSH private key to authenticate as `bandit26`:

- `ssh -i bandit26.sshkey bandit26@bandit.labs.overthewire.org -p 2220` — use the `-i` option to specify the private key file when connecting.
- Ensure the key has restrictive permissions before use: `chmod 600 bandit26.sshkey` (OpenSSH rejects keys that are world-readable).
- If you prefer using an agent: `ssh-add bandit26.sshkey` then `ssh bandit26@... -p 2220` (use `ssh -o IdentitiesOnly=yes -i ...` to force that key if needed).

Troubleshooting and safety:

- If authentication fails, confirm the key file and username are correct and that the key matches the server-side authorized key.
- Do not commit private keys or discovered passwords to version control; keep the key private and remove it when finished.
- For repeatable automation, use `-o IdentitiesOnly=yes` to avoid ssh trying other keys first: `ssh -o IdentitiesOnly=yes -i bandit26.sshkey bandit26@... -p 2220`.

---
````
