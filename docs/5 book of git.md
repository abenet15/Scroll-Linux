# 📖 Book of Git

---

## 1️⃣ Install Git

```bash
sudo apt update
sudo apt install git -y
git --version
```

> Configure User

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

## 2️⃣ Create github Repo

## 3️⃣ Create Local Repo

> create directory

```bash
mkdir Scroll-Linux
cd Scroll-Linux
```

> create a new repository 

```bash
echo "# Scroll-Linux" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/abenet15/Scroll-Linux.git
git push -u origin main
```

> push an existing repository

```bash
git remote add origin https://github.com/abenet15/Scroll-Linux.git
git branch -M main
git push -u origin main
```
