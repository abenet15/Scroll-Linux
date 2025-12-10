# 📜 Scroll of Python HTTP Server Magic

## 🐍 Summoning the Server

```bash
python3 -m http.server 9000
```

- Starts a web server on port **9000**.
- Serves files from the current directory.
- Logs every request in your terminal.

---

## 🌐 Why It Works

- **Python’s Standard Library** includes `http.server`.
- It automatically:
  - Serves `index.html` if present.
  - Otherwise generates a **directory listing in HTML**.

---

## 🔍 Accessing the Server

- Find your PC’s IP:
  
  ```bash
  ip a
  ```
  
  Example: `192.168.194.82`

- On your phone’s browser:
  
  ```
  http://192.168.194.82:9000
  ```

---

## 🏠 Local Names Instead of IP

- **Option 1: `/etc/hosts`**
  
  ```
  192.168.194.82 myserver.local
  ```
  
  → Access via `http://myserver.local:9000`

- **Option 2: Avahi/mDNS**
  
  ```bash
  sudo apt install avahi-daemon
  ```
  
  → Access via `http://<hostname>.local:9000`

---

## 🧪 Experiments

- Add `index.html` → custom homepage.

- Share files → direct links like:
  
  ```
  http://192.168.194.82:9000/notes.txt
  ```

- Change port:
  
  ```bash
  python3 -m http.server 8080
  ```

---

## 📓 Quick Reference

- **Start server:** `python3 -m http.server <port>`
- **Default behavior:** directory listing or `index.html`
- **Access:** `http://<PC-IP>:<port>`
- **Local name:** `/etc/hosts` or Avahi `.local`

---

✨ That’s your scroll — a compact, reproducible recipe for conjuring local web servers with Python.

Would you like me to extend this scroll into a **“Book of Local Web Servers” section** with diagrams (like flow of request: Phone → Hotspot → Ubuntu → Python server), so you can visualize the magic too?
