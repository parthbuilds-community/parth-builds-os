
# Fixing "ERESOLVE unable to resolve dependency tree" in Vite + Tailwind

If you are building a **React + Vite + Tailwind project**, you may face this common error:

```
ERESOLVE unable to resolve dependency tree
````

This happens due to **version conflicts**:

- Your project may have **Vite 8** installed
- `@tailwindcss/vite` plugin supports only **Vite 5, 6, or 7**
- `@vitejs/plugin-react` may require **Vite 8** → causes conflict

---

## ✅ Step-by-Step Fix

### 1️⃣ Remove conflicting Vite / React plugin
```bash
npm uninstall vite @vitejs/plugin-react
````

### 2️⃣ Install compatible versions

```bash
npm install -D vite@7
npm install -D @vitejs/plugin-react@5
```

### 3️⃣ Install Tailwind

```bash
npm install tailwindcss @tailwindcss/vite
```

---

## ⚙️ Configure Vite

`vite.config.js`:

```javascript
import { defineConfig } from 'vite'
import react from '@vitejs/plugin-react'
import tailwindcss from '@tailwindcss/vite'

export default defineConfig({
  plugins: [react(), tailwindcss()],
})
```

---

## 🖌️ Setup CSS

Create `src/index.css`:

```css
@import "tailwindcss";
```

Import it in `main.jsx`:

```javascript
import './index.css';
```

---

## 🎯 Done!

Now your project should run perfectly with:

* **Vite 7**
* **React plugin v5**
* **Tailwind v4 + @tailwindcss/vite**

Run:

```bash
npm run dev
```

Your terminal should be green, and Tailwind should work flawlessly.

---

💡 **Tip:** Save this guide for future projects — dependency conflicts like this happen often when upgrading Vite or Tailwind!

## 🤝 Contributing

Found an amazing resource? Want to add your favorite course? Check out our [CONTRIBUTING.md](../CONTRIBUTING.md) to learn how you can help grow this collection!

## 🔗 Connect With Me

[![Instagram](https://img.shields.io/badge/Instagram-E4405F?style=for-the-badge&logo=instagram&logoColor=white)](https://instagram.com/parth.builds)
[![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/parthnarkar)
[![LinkedIn](https://img.shields.io/badge/-LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/parthnarkar)
[![LeetCode Profile](https://img.shields.io/badge/LeetCode-ParthNarkar-FFA116?style=for-the-badge&logo=leetcode)](https://leetcode.com/u/parthnarkar/)
[![Email](https://img.shields.io/badge/-Email-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:parthnarkarofficial@gmail.com)
[![Twitter](https://img.shields.io/badge/-Twitter-1DA1F2?style=for-the-badge&logo=twitter&logoColor=white)](https://twitter.com/parthnarkar)
[![Discord](https://img.shields.io/badge/-Discord-5865F2?style=for-the-badge&logo=discord&logoColor=white)](https://discord.com/users/parth_narkar)

### ⭐ Found this helpful? Give this Repo a STAR!

[![parth-builds-os Github Repo Footer](https://github.com/user-attachments/assets/4bef3a04-16ee-4484-a52c-4f31182e1916)](https://github.com/parthnarkar/parth-builds-os)
