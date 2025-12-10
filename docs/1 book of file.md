---
layout: default
title: Book of Git
---

# 📚 Book of files

---

**Linux Filesystem**

> / (root)
> ├── bin                          # Essential system binaries
> ├── etc                          # System-wide configuration files
> ├── lib                           # Shared libraries for system programs
> ├── home                     # User home directories
> ├         └─ username    # Personal files for user 'username'
> ├         └─ username
> 
> └── usr                          # User-related programs and files

## 1, Navigation

```bash
cd       # Change directory
pwd      # Print working directory
ls       # List files
tree     # Show directory tree
find     # Search for files
```

---

## 2, Files

Create a new empty file

```bash
touch newfile.txt
```

mkdir MyFolder

```bash
mkdir    
```

Remove files or directories

```bash
rm file.txt        
rm -r folder
```

copy

```bash
cp source.txt destination.txt      
```

Move or rename files

```bash
mv oldname.txt newname.txt 
```

---

## Editors

```text
Editor Commands
├── nano     # Simple text editor
├── vim      # Advanced editor
├── less     # View file contents
├── cat      # Print file contents
├── head     # First lines of file
└── tail     # Last lines of file
```
