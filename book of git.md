# 📖 Book of Git

---

## 1️⃣ Install Git

```bash
sudo apt update
sudo apt install git -y
git --version
```

---

## 2️⃣ Configure User

```bash
git config --global user.name "Abenet"
git config --global user.email "your_email@example.com"
```

- **user.name** → your Git identity
- **user.email** → must match your GitHub email

Check settings:

```bash
git config --list
```

---

## 3️⃣ Create Local Repo

```bash
mkdir Scroll-Linux
cd Scroll-Linux
git init
```

> Creates a `.git` folder → marks it as a repo.

---

## 4️⃣ Connect to GitHub

```bash
git remote add origin https://github.com/YourUser/Scroll-Linux.git
```

---

## 5️⃣ First Commit & Push

```bash
echo "# Scroll-Linux Notes" >> README.md
git add .
git commit -m "Initial commit: Book of Git"
git push -u origin main
```

---

## Summery

| Task           | Command                                  |
|:-------------- | ---------------------------------------- |
| Install Git    | `sudo apt install git -y`                |
| Check version  | `git --version`                          |
| Set identity   | `git config --global user.name "Abenet"` |
| Init repo      | `git init`                               |
| Add remote     | `git remote add origin <URL>`            |
| Commit changes | `git commit -m "message"`                |
| Push to GitHub | `git push -u origin main`                |

---
