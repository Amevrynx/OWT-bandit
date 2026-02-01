## Access Information

SSH Portal:
ssh bandit15@bandit.labs.overthewire.org -p 2220

Website:
https://overthewire.org/wargames/bandit/

Password for each level is stored inside the current level and used to log into the next.

---

## Level 15 → 16

### Steps to solve
```bash
openssl s_client -connect localhost:30001
then submit the password for the current level 
            or 
cat /etc/bandit_pass/bandit15 | openssl s_client -connect localhost:30001
```


### explanation

This level uses OpenSSL's `s_client` to open an SSL/TLS connection to a local service and submit the current level's password over the encrypted channel.

- `openssl s_client -connect localhost:30001` — opens a TLS connection to `localhost` on port `30001`. The command negotiates TLS and then presents an interactive session where you can read the server's output and type input to send.

Usage details and variations:

- To interactively submit the password, run `openssl s_client -connect localhost:30001`, then type or paste the password followed by Enter. The server will respond over the secure connection.
- To non-interactively submit the password from a file, pipe or redirect the password into `s_client`:

    - `cat /etc/bandit_pass/bandit15 | openssl s_client -connect localhost:30001` — sends the password read from the file into the TLS session. Be careful with file permissions and the presence of trailing newlines when piping.
    - Alternatively: `openssl s_client -connect localhost:30001 < /etc/bandit_pass/bandit15`.
---