# 📖 Book of Permissions

---

## 1, Check permission with

```bash
ls -l /home/abi/work
```

> out put
> 
> ```text
> total 4
> drwxr-xr-x 18 abi abi 4096 Nov 28 12:39 FullTimeAddis
> ```

- **d** → type = directory

- **rwxr-xr-x** → permissions
  
  - User (owner) → `rwx` = read, write, execute
  
  - Group → `r-x` = read, execute
  
  - Others → `r-x` = read, execute

## 2, 🔓 Fix Locked Files

---

1️⃣ Recursive (`-R`)

```bash
chmod -R 755 /home/abi/work/FullTimeAddis
```

2️⃣ Non‑recursive

```bash
chmod 755 /home/abi/work/FullTimeAddis
```

- **`chmod`** → changes file permissions.

- **`-R`** → recursive, applies to all files and subfolders inside.

- **`755`** → means:
  
  - User → **rwx**
  - Group → **rx**
  - Others → **rx**

> **Effect:** Directory is accessible to everyone, but only you can modify it. This is the standard for most Linux folders.

---

1️⃣ Recursive (`-R`)

```bash
chown -R abi /home/abi/work/FullTimeAddis
```

2️⃣ Non‑recursive

```bash
chown abi /home/abi/work/FullTimeAddis
```

- **`chown`** → changes ownership of files.
- **`-R`** → recursive, applies to everything inside.
- **`abi`** → sets you as the owner.

> **Effect:** Removes the “lock icon” problem by ensuring the folder belongs to your user account instead of `root` or some unknown Windows SID.

---

## 4, Mask Creation

```bash
umask 022
```

- **`022`** → means:
  - **First digit (0)** → User (owner)
  - **Second digit (2)** → Group
  - **Third digit (2)** → Others

> **Effect:** Keeps files safe: editable by you, readable by others

Sets default permissions for new files/dirs, Removes write for group & others

Files → 644 (rw for user, r for group/others)

Dirs → 755 (rwx for user, rx for group/others)

---

## 5, 📖 Permission Numbering (Cheat‑Note)

### 🔢 Basics

```text
U G O → User, Group, Others

Digits = sum of bits:
4 = read (r)
2 = write (w)
1 = execute (x)
```

### Examples

```text
7 = rwx
6 = rw-
5 = r-x
4 = r--
0 = ---
```

---

### 🔑 Quick Defaults

- **Files:** `644` → user rw, group/others r  
- **Dirs:** `755` → user rwx, group/others rx  
- **Private:** `700` → only user full access  

---

# summary

| Task              | Command Example                           | Result              |
| ----------------- | ----------------------------------------- | ------------------- |
| Check permissions | ls -l /home/abi/work                      | Show rights + owner |
| Fix perms (all)   | chmod -R 755 /home/abi/work/FullTimeAddis | User rwx, others rx |
| Fix owner (all)   | chown -R abi /home/abi/work/FullTimeAddis | Sets abi as owner   |
| Default mask      | umask 022                                 | Files 644, dirs 755 |
