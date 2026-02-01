<img src="https://raw.githubusercontent.com/Amevrynx/OWT-bandit/main/bandit21/image.png">

### explanation

## bandit21

````markdown
## Access Information

SSH Portal:
ssh bandit21@bandit.labs.overthewire.org -p 2220

Website:
https://overthewire.org/wargames/bandit/

Password for each level is stored inside the current level and used to log into the next.

---

## Level 21 → 22

### Steps to solve
```bash
ls
cat /etc/cron.d
cat cronjob_bandit22
cd /usr/bin
cat cronjob_bandit22.sh
cat /tmp/filename
```
---
<img src="https://raw.githubusercontent.com/Amevrynx/OWT-bandit/main/bandit21/image.png">

### explanation

These commands investigate a cron job that writes the next-level password to a predictable temporary file.

- `ls` — list files in the current directory to see what is provided for the level (e.g., `cronjob_bandit22`).
- `cat /etc/cron.d` — list cron drop-in files to find scheduled jobs; look for an entry that references `cronjob_bandit22` or a user that runs it.
- `cat cronjob_bandit22` — display the cron file shipped for this level; it shows the schedule and the command cron will run. Note the exact command path and any arguments.
- `cd /usr/bin` and `cat cronjob_bandit22.sh` — change to the directory containing the script referenced by the cron job and inspect the script source. The script usually runs as a privileged user via cron and may write output to `/tmp` or another predictable location.
- `cat /tmp/filename` — read the temporary file the script writes (the password). Cron-run scripts often create files in `/tmp` with predictable names; if the cron job runs periodically the file will be present after the job executes.

---
````
