### 🔧 book of apt

---

**APT (Advanced Package Tool)** is the package manager used in Debian/Ubuntu systems.

- **install app**
  update
  
  ```bash
  sudo apt update
  ```
  
  > sudo apt update will:
  > 
  > - Connects to all configured repositories (the sources listed in /etc/apt/sources.list and /etc/apt/sources.list.d/
  > - Downloads the latest metadata about packages (names, versions, dependencies).
  > - Updates the local cache stored in /var/lib/apt/lists/
  >   install app
  
  ```bash
    sudo apt install app
  ```
  
  ```bash
    sudo apt install app -y
  ```
  
  - flag -y means Do you want to continue? [Y/n]
  
  some packages are not in list of debian so you might need
  
  ```bash
  sudo snap install marktext
  ```

- **Reinstall app**
  
  remove snap app
  
  ```bash
  sudo snap remove app
  ```
  
  removes internal package
  
  ```bash
  sudo apt purge app
  ```
  
  update
  
  ```bash
  sudo apt update
  ```
  
  install app
  
  ```bash
  sudo apt install app
  ```
  
  This removes the package and reinstalls it cleanly.
  
  ---

- **Repair your package system**  
  
  > If you suspect broken dependencies:
  
  ```bash
  sudo apt --fix-broken install
  sudo apt update && sudo apt upgrade
  ```

---
