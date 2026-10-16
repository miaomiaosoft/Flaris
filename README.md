# Flaris 🧭
> **Your bookmark galaxy on the edge.**

[![Cloudflare Workers](https://img.shields.io/badge/Cloudflare-Workers-orange?logo=cloudflare&logoColor=white)](https://workers.cloudflare.com)
[![Vue.js](https://img.shields.io/badge/Vue.js-3.0-4FC08D?logo=vuedotjs&logoColor=white)](https://vuejs.org)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind-CSS-38B2AC?logo=tailwindcss&logoColor=white)](https://tailwindcss.com)
[![License](https://img.shields.io/badge/license-MIT-blue)](https://github.com/zaocat/Flaris?tab=MIT-1-ov-file)

![Light Mode](screenshots/light.png)

<p align="center">Light Mode screenshot</p>

![Dark Mode](screenshots/dark.png) 

<p align="center">Dark Mode screenshot</p>

[English](#english) | [中文说明](#chinese)

---

<a name="english"></a>
## 📖 English

**Flaris** is a lightweight, serverless, and highly customizable personal navigation/start page running entirely on **Cloudflare Workers**. It uses **Cloudflare KV** for data storage, meaning you get a fast, secure, and free personal dashboard without managing any servers or databases.

With a single `worker.js` file, Flaris delivers a robust admin panel featuring visual editing, drag-and-drop sorting, private links, and internationalization (i18n), all wrapped in a beautiful glassmorphism UI.

### 🌟 Origin of the name Flaris: 

Combination of Flare (Cloudflare) and Polaris (North Star). 

Meaning: The guiding star on Cloudflare. 

Commentary: It sounds very sophisticated and elegant, fitting the image of a "navigator".

### ✨ Features

* **☁️ Serverless:** Hosted 100% on Cloudflare Workers (Free Tier friendly).
* **⚡ Single File:** The entire logic (Frontend + Backend) is contained in a single `worker.js` file.
* **🎨 Modern UI:** Glassmorphism design, responsive layout (Mobile/Desktop), and smooth transitions.
* **🌗 Dark/Light Mode:** Automatic detection with a manual toggle switch.
* **🌍 Internationalization (i18n):** Built-in English and Chinese support, auto-synced between views.
* **🔒 Admin Panel:**
    * Secure login protection.
    * **Visual Editing:** Add/Edit/Delete Categories and Links visually.
    * **Drag & Drop Sorting:** Easily reorder categories and items.
    * **Icons:** Built-in FontAwesome selector and custom image URL support.
    * **Private Links:** Hide sensitive links from visitors (visible only to admin).
    * **Batch Selection:** Add existing items from the pool to multiple categories.
* **💾 Backup & Restore:** One-click JSON export/import to keep your data safe.
* **🔍 Global Search:** Real-time filtering of all links.

### 🚀 Deployment Guide (Latest UI)

1.  **Create Worker:**
    * Log in to the Cloudflare Dashboard.
    * Go to **Compute (Worker & Pages)** -> **Overview**.
    * Click **Create** -> **Create Worker**.
    * Name it (e.g., `flaris`) and click **Deploy**.

2.  **Create KV Namespace:**
    * Go to the sidebar menu **Storage & Databases** -> **Workers KV**.
    * Click **Create a Namespace**.
    * Name it `NAV_KV` (or any name you like) and click **Add**.

3.  **Bind KV & Set Password:**
    * Go back to your Worker (`Compute` -> `Workers & Pages` -> Select your worker).
    
    * **Step A: Bind KV**
        * Click the **Settings** (or **Bindings**) tab.
        * Scroll to **Bindings** (or click "Add binding").
        * Click **Add** -> **KV Namespace**.
        * **Variable name:** `NAV_DB` (**Must be exactly this**).
        * **KV Namespace:** Select the `NAV_KV` you created in step 2.
        * Click Save.

    * **Step B: Set Password**
        * Click the **Settings** tab -> **Variables**.
        * Click **Add variable**.
        * **Variable name:** `ADMIN_PASSWORD`.
        * **Value:** Your desired password (e.g., `123456`).
        * Click Save.

4.  **Upload Code:**
    * Click the **Edit code** button (top right).
    * Delete the existing code in `worker.js`.
    * Copy and paste the entire content of `worker.js` from this repository.
    * Click **Deploy** (top right).

5.  **Enjoy!**
    * Visit your Worker URL.
    * Click the **Shield Icon** (top right) or **Menu** (mobile) to login.

---

<a name="chinese"></a>
## 🇨🇳 中文说明

**Flaris** 是一个追求极致简约与高性能的现代化无服务器导航站。它完全运行在 **Cloudflare Workers** 上，使用 **KV 存储** 数据。这意味着你无需购买服务器或数据库，就能拥有一个快速、安全且免费的个人仪表盘。

仅需一个 `worker.js` 文件，Flaris 就提供了强大的后台管理功能，包括可视化编辑、拖拽排序、私有链接保护以及中英文国际化支持，并拥有精美的磨砂玻璃 UI 设计。

### 🌟 Flaris 名字由来

组合：Flare (Cloudflare) + Polaris (北极星)

含义：Cloudflare 上的指路明星。

点评：听起来非常高级、优雅，符合“导航/指引”的寓意，同时包含了 Cloudflare 的元素。

### ✨ 功能特性

* **☁️ Serverless 架构:** 100% 运行在 Cloudflare Workers 上（免费版额度足够个人使用）。
* **⚡ 单文件部署:** 前后端逻辑包含在一个 `worker.js` 文件中，极易维护。
* **🎨 现代化 UI:** 磨砂玻璃质感，响应式布局（完美适配手机/桌面），丝滑的动画效果。
* **🌗均色/暗黑模式:** 支持日间/夜间模式切换，且配置持久化。
* **🌍 多语言 (i18n):** 内置中英文切换，前后台语言自动同步。
* **🔒 强大的管理后台:**
    * 安全登录保护。
    * **可视化编辑:** 直观地添加、修改、删除栏目和链接。
    * **拖拽排序:** 支持栏目和内容的上下移动排序。
    * **图标选择器:** 内置常用 FontAwesome 图标，也支持自定义图片 URL（自动识别 Logo）。
    * **私有链接:** 可将特定链接设为“私有”，仅管理员登录后可见（访客端自动过滤，保护隐私）。
    * **批量关联:** 支持从内容池中多选已有链接添加到不同分类。
* **💾 备份与恢复:** 支持一键导出 JSON 备份数据，或导入 JSON 恢复数据。
* **🔍 全局搜索:** 顶部自带搜索框，实时过滤所有链接。

### 🚀 部署教程 (最新版控制台)

1.  **创建 Worker:**
    * 登录 Cloudflare 控制台。
    * 在左侧菜单找到 **计算 (Workers 和 Pages)** -> **概述**。
    * 点击 **创建应用程序** -> **创建 Worker**。
    * 给它起个名字（例如 `flaris`），然后点击 **部署**。

2.  **创建 KV 存储:**
    * 在左侧菜单找到 **存储和数据库** -> **Workers KV**。
    * 点击 **创建命名空间**。
    * 输入名称 `NAV_KV` (或者你喜欢的名字)，点击 **添加**。

3.  **绑定 KV 与设置密码:**
    * 回到你刚才创建的 Worker 页面 (`计算` -> `Workers 和 Pages` -> 选择你的 Worker)。
    
    * **步骤 A: 绑定 KV 数据库**
        * 点击 **设置 (Settings)** 标签页 -> **绑定 (Bindings)** (或者直接点击顶部的 **绑定** 标签)。
        * 点击 **添加 (Add)** -> **KV 命名空间**。
        * **变量名称 (Variable name):** 填写 `NAV_DB` (**必须完全一致，注意大写**)。
        * **KV 命名空间:** 选择你在第 2 步创建的 `NAV_KV`。
        * 点击保存。

    * **步骤 B: 设置后台密码**
        * 点击 **设置 (Settings)** 标签页 -> **变量 (Variables)**。
        * 点击 **添加变量 (Add variable)**。
        * **变量名称:** 填写 `ADMIN_PASSWORD`。
        * **值:** 填写你想要的后台登录密码 (例如 `123456`)。
        * 点击保存。

4.  **上传代码:**
    * 点击右上角的 **编辑代码 (Edit code)** 按钮。
    * 删除编辑器中默认的 hello world 代码。
    * 将本项目 `worker.js` 的所有代码复制粘贴进去。
    * 点击右上角的 **部署 (Deploy)**。

5.  **开始使用:**
    * 访问你的 Worker 域名。
    * 点击右上角的 **盾牌图标** (管理后台) 或移动端的菜单按钮进行登录。
    * 输入刚才设置的密码即可开始配置你的 Flaris 导航站！

### 🛠️ 常见问题

* **如何修改网站标题和 Logo？**
    * 登录后台后，点击左下角的 **“设置”** 按钮，在弹窗中可以修改前台标题、后台标题、Logo、Favicon 以及 GitHub 地址等。
* **私有链接是什么？**
    * 在添加或编辑链接时，勾选“私有链接”。该链接在未登录状态下不会加载，也不会出现在网页源码中，适合存放 NAS、路由器后台等敏感地址。
* **如何自定义 CSS/JS？**
    * 在“站点设置”的“高级”选项卡中，你可以注入自定义的 CSS 样式或 JavaScript 代码（用于添加统计代码、修改字体等）。

## 📄 License

[MIT License](https://github.com/zaocat/Flaris?tab=MIT-1-ov-file)
