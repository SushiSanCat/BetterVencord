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

### 1. Prerequisites
- [Node.js (LTS recommended)](https://nodejs.org/en)
- [pnpm](https://pnpm.io/installation)

### 2. Clone the Source
```sh
git clone https://github.com/Davilarek/Vencord.git
cd Vencord
```

### 3. Compile
```sh
pnpm install --frozen-lockfile
pnpm build --standalone
# For web usage (optional):
pnpm buildWeb --standalone
```
- Compiled files will be in the `dist` folder. Keep this folder intact for BetterVencord to work.

### 4. Install Vencord
- Run [Vencord's official installer](https://github.com/Vendicated/Vencord#installing--uninstalling).
- **Windows:** If your Discord install path is protected, run the installer as admin.

### 5. Copy Files
- **Backup your Vencord user data!**
  - Linux: `$XDG_CONFIG_HOME/Vencord/` (usually `~/.config/Vencord/`)
  - Windows: `%appdata%/Vencord`
- Copy your compiled `dist` folder into your Vencord user data directory.

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

> "it's called Vencord because it's made by ven,<br> it's called BetterVencord because it's better than Vencord"<br> <sub>- Davilarek</sub>
