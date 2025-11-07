# screen_summary
Sure — here’s a clean, short text summary you can save or paste in your notes:

---

### Running Code in Background with `screen`

1. **Create a screen session:**

   ```bash
   screen -S mysession
   ```

2. **Run your code inside the session:**

   ```bash
   python my_script.py
   ```

3. **Detach (leave it running):**
   Press `Ctrl + A`, then `D`.

4. **List active sessions:**

   ```bash
   screen -ls
   ```

5. **Reattach to a session:**

   ```bash
   screen -r mysession
   ```

6. **Close a session:**
   Type `exit` or press `Ctrl + D`.

**Tip:**
Use logging with:

```bash
screen -L -S mysession
```

This saves output to `screenlog.0`.

Your code keeps running even if you disconnect — just reconnect and use `screen -r` to resume.

---

Would you like me to make it even more compact (e.g., for a quick reference note or command cheat sheet)?
