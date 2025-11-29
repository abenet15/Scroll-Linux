# safe process for renaming a user in Ubuntu

---

## 1. Create a Temporary Admin Account

```bash
sudo adduser tempadmin
sudo usermod -aG sudo tempadmin
```

- `tempadmin` is a backup account with sudo privileges.
- You’ll use it to rename your main account while it’s not in use.

give it sudo power

```bash
sudo usermod -aG sudo tempadmin
```

cheak it in sudo group

```bash
groups tempadmin
```

---

## 2. Log Out and Switch to `tempadmin`

- Log out of your current account (e.g., `abi` or `aiy`).
- Log in as `tempadmin`.

---

## 3. Rename the User

Run these commands as `tempadmin`:

```bash
# Rename login name abi to abenet
sudo usermod -l abenet abi

# Rename home directory and move files
sudo usermod -d /home/abenet -m abenet

# Rename group if it matches old username
sudo groupmod -n abenet abi
```

---

## 4. Reboot

```bash
sudo reboot
```

After reboot, log in as your new user (`abenet`).

---

## 6. change the comment

the ui use name in comment so you have to change it to.

```bash
sudo usermod -c "Abenet" abi
```

## 7. Remove Temporary Account (Optional)

Once you’re sure everything works:

```bash
sudo deluser tempadmin
sudo rm -r /home/tempadmin
```

---

## ⚠️ Notes

- Always back up your home folder before renaming.
- If you skip the home directory step, the new user will still point to the old folder.
- Recovery mode can also be used if you don’t want to create a temporary account.
