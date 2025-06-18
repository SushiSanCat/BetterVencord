# 🚀 **BetterVencord**

> **A Forceful Blend of Discord Awesomeness!**

![BetterVencord Banner](https://github.com/Davilarek/Vencord/assets/62715937/7126afa2-6086-4675-9427-e3f0cf542651)

<p align="center">
  <img src="https://img.shields.io/github/stars/Davilarek/Vencord?style=social" alt="GitHub stars">
  <img src="https://img.shields.io/badge/Platform-Discord-blue" alt="Platform">
  <img src="https://img.shields.io/badge/License-MIT-green" alt="License">
</p>

---

## 📚 Table of Contents
- [About](#about)
- [Features](#features)
- [Installation](#installation)
- [Troubleshooting](#troubleshooting)
- [Using BetterVencord](#using-bettervencord)
- [Importing & Managing BD Plugins](#importing--managing-bd-plugins)
- [Uninstalling](#uninstalling)
- [Updating](#updating)
- [Disclaimer](#disclaimer)
- [Adding Custom Plugins in BetterVencord](#adding-custom-plugins-in-bettervencord)

---

## 🌌 About
**BetterVencord** is the ultimate fusion of [BetterDiscord](https://betterdiscord.app/) and [Vencord](https://vencord.dev/), bringing you the best of both worlds:
- Seamless plugin support
- Custom themes
- Enhanced privacy
- Cross-platform compatibility

> **Note for Plugin Developers:**
> Don't fork this repo to make plugins for Vencord. We regularly pull from upstream. If you want your plugin in BV, just wait for us to sync.

---

## ✨ Features
- **Easy Installation**
- **100+ Built-in Plugins** ([Browse Plugins](https://vencord.dev/plugins))
- **Lightweight** despite many features
- **Browser Support:** Use as extension or UserScript
- **Works on All Discord Branches:** Stable, Canary, PTB
- **Custom CSS & Themes:** Import any CSS, including BetterDiscord themes
- **Privacy Friendly:** Blocks Discord analytics & crash reporting, no telemetry
- **Active Maintenance:** Broken plugins usually fixed within 12 hours
- **Settings Sync:** Sync plugins/settings across devices (optional)
- **BD API Compatibility:** Run most BetterDiscord plugins natively!

> **External Sources Used:**
> - [BrowserFS](https://github.com/jvilk/BrowserFS)
> - [BetterDiscord code](https://github.com/Davilarek/Vencord/blob/main/src/plugins/bdCompatLayer/stuffFromBD.js)

---

## ⚡ Installation

Follow these detailed steps to install BetterVencord. Each step is specific to ensure a smooth setup process.

---

### 1. Prerequisites

Before you begin, make sure you have the following installed on your system:

- **Node.js (LTS version recommended):**  
  Download and install from [nodejs.org](https://nodejs.org/en).  
  To check if Node.js is installed, open your terminal (Command Prompt on Windows, Terminal on macOS/Linux) and run:
  ```sh
  node -v
  ```
  You should see a version number (e.g., `v18.18.0`).

- **pnpm (package manager):**  
  Install pnpm by running the following command in your terminal:
  ```sh
  npm install -g pnpm
  ```
  To verify installation, run:
  ```sh
  pnpm -v
  ```
  You should see a version number (e.g., `8.10.2`).

  Or, if you prefer, you can visit the [pnpm installation page](https://pnpm.io/installation) for more options and instructions.

---

### 2. Clone the Source Code

1. **Open your terminal** (Command Prompt, PowerShell, or Terminal).

2. **Navigate to the directory** where you want to download BetterVencord. For example:
   ```sh
   cd ~/Downloads
   ```
3. **Clone the repository** by running:
   ```sh
   git clone https://github.com/SushiSanCat/BetterVencord.git
   ```
4. **Enter the project directory:**
   ```sh
   cd BetterVencord
   ```

---

### 3. Install Dependencies and Build

1. **Install all required dependencies** (this will use the versions locked in the repository):
   ```sh
   pnpm install --frozen-lockfile
   ```
2. **Build BetterVencord for desktop usage:**
   ```sh
   pnpm build --standalone
   ```
   - This will generate the compiled files in the `dist` folder.

2. **(Optional) Build for web usage:**  
   If you want to use BetterVencord as a browser extension or UserScript, run:
   ```sh
   pnpm buildWeb --standalone
   ```

> **Note:**  
> Do **not** delete or move the `dist` folder after building. All necessary files for BetterVencord to function are inside.

---

### 4. Install Vencord

1. **Download and run the official Vencord installer:**  
   Go to [Vencord's official installation page](https://github.com/Vendicated/Vencord#installing--uninstalling) and follow the instructions for your operating system.

2. **Windows users:**  
   - If you receive a permissions error or your Discord install path is protected, **right-click the installer and select "Run as administrator"**.

---

### 5. Copy Compiled Files to Vencord User Data

1. **Backup your existing Vencord user data** (highly recommended):
   - **Linux:**  
     Your data is usually in `$XDG_CONFIG_HOME/Vencord/` (commonly `~/.config/Vencord/`).
   - **Windows:**  
     Your data is in `%appdata%/Vencord` (e.g., `C:\Users\<YourName>\AppData\Roaming\Vencord`).

   To back up, simply copy the entire `Vencord` folder to a safe location.

2. **Copy the compiled `dist` folder:**
   - After building, locate the `dist` folder inside your `BetterVencord` project directory.
   - Copy the entire `dist` folder and paste it into your Vencord user data directory:
     - **Linux:** `~/.config/Vencord/`
     - **Windows:** `%appdata%\Vencord\`
   - If prompted, choose to overwrite existing files.

3. **Restart Discord** to apply the changes.

---

**You have now installed BetterVencord!**  
If you encounter any issues, refer to the Troubleshooting section below.

---

## 🛠️ Troubleshooting

### **pnpm Version Error**
> **Error:**
> `ERR_PNPM_BAD_PM_VERSION  This project is configured to use v8.10.2 of pnpm. Your current pnpm is v9.1.0`

**Solutions:**
- Set `COREPACK_ENABLE_STRICT=0` (Linux: `export`, Windows: `set`)
- Downgrade to pnpm 8.10.2
- (Not recommended) Edit `package.json` to match your pnpm version

### **Filesystem Failed to Load?**
#### **Issue 1: CORS Proxy Error**
- Check console for CORS errors near `PluginManager Starting plugin BD Compatibility Layer`.
- **Fix:** Find a working CORS proxy URL, set it in BD Compat Layer settings, and reload.

#### **Issue 2: Out of Memory**
- If using "Use Indexed DB Instead" and have low RAM/disk, you may see this error.
- **Fix:** Add more RAM or free up space.

#### **Issue 3: Large Data in Virtual Filesystem**
- If not using IndexedDB and storing >10MB, you may hit localStorage limits.
- **Fix:** Migrate to IndexedDB if possible.

---

## 🚀 Using BetterVencord
- Functions like Vencord, but with a **BD Compatibility Layer** under Plugins.
- **Enable BD Compatibility Layer** to use BetterDiscord plugins.
- Once enabled, you'll see a "Virtual Filesystem" menu under Backup & Restore.

---

## 📦 Importing & Managing BD Plugins

### **First Time Import**
> **Important:** Most BD plugins require [ZeresPluginLibrary](https://github.com/rauenzi/BDPluginLibrary). Download and import it first.

**To Import:**
1. In Virtual Filesystem, left-click `/`, then `BD`, then right-click `plugins` → Import a file here.
2. Collapse and expand the plugins folder to confirm import.
3. Click **Reload BD Plugins** to activate.

**If a plugin doesn't appear:**
- It may not be compatible. Remove it as above.

### **Removing BD Plugins**
1. Right-click the plugin in Virtual Filesystem → Delete file.
2. Collapse/expand to confirm removal.
3. Click **Reload BD Plugins**.

---

## 🧹 Uninstalling
- Use Vencord's official installer to uninstall.
- If that fails, revert your Vencord user data, then run the installer again.
- No backup? Delete your Vencord user data directory, reinstall, then uninstall.

---

## 🔄 Updating
1. `cd` to your cloned source directory.
2. Run:
```sh
git fetch
git pull
```
3. Repeat the compile steps above.

---

## ⚠️ Disclaimer
> **Discord is a trademark of Discord Inc.**
> This project is not affiliated with or endorsed by Discord Inc.

<details>
<summary>Using Vencord violates Discord's Terms of Service</summary>

- Client mods are against Discord's ToS.
- Discord is generally indifferent; no known bans for using Vencord.
- Avoid abusive plugins and posting screenshots in sensitive servers.
- If your account is critical, avoid client mods to be safe.

</details>

---

## 🛑 **Read This Before Using!**
> To run BetterDiscord plugins on Vencord, you **must enable the BD Compatibility Layer** plugin first. Without it, BD plugins will not work!

---

## 🧩 Adding Custom Plugins in BetterVencord

Follow these steps to add custom plugins (such as ZeresPluginLibrary) in BetterVencord:

1. **Open Discord.**
2. **Go to User Settings** (the gear icon at the bottom left).
3. **Scroll down to the Vencord section** in the sidebar and click on **Plugins**.
4. **Enable the "BD Compatibility Layer" plugin.**
5. **Click the cog wheel** (⚙️) next to the BD Compatibility Layer plugin to open its settings.
6. **In the settings, find the field labeled `Plugin Url 1`.**
7. **Copy and paste the following link into `Plugin Url 1`:**
   ```
   @https://raw.githubusercontent.com/SushiSanCat/BDPluginLibrary/refs/heads/master/release/0PluginLibrary.plugin.js
   ```
8. **Click "Save & Close"** to apply the changes.
9. **Restart Discord** to ensure the plugin is loaded.
10. **Go back to User Settings → Vencord → Plugins.**
11. **Find and enable the "ZeresPluginLibrary" plugin** (it should now appear in your plugin list).

You can now import and use most BetterDiscord plugins in BetterVencord!

> **Tip:** Always make sure the BD Compatibility Layer and ZeresPluginLibrary are enabled for maximum compatibility with BD plugins.

---

> "it's called Vencord because it's made by ven,<br> it's called BetterVencord because it's better than Vencord"<br> <sub>- Davilarek</sub>
